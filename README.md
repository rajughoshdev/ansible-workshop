# Ansible Roles Example
### Starting examples of the ansible playbook, features and how they work together.

Ansible is a radically simple IT automation engine that automates cloud provisioning, configuration management, application deployment, intra-service orchestration, and many other IT needs.

Being designed for multi-tier deployments since day one, Ansible models your IT infrastructure by describing how all of your systems inter-relate, rather than just managing one system at a time.

It uses no agents and no additional custom security infrastructure, so it's easy to deploy - and most importantly, it uses a very simple language (YAML, in the form of Ansible Playbooks) that allow you to describe your automation jobs in a way that approaches plain English.

On this page, we'll give you a really quick overview so you can see things in context. For more detail, hop over to [docs.ansible.com](https://docs.ansible.com)

### Installing ansible on ubuntu
<pre>
sudo apt-get install software-properties-common

sudo apt-add-repository ppa:ansible/ansible

sudo apt-get update

sudo apt-get install ansible
</pre>

## Inventory Setup

Ansible uses a simple [inventory system](https://docs.ansible.com/ansible/latest/user_guide/intro_inventory.html) to manage your hosts. This allows you to organise hosts into logical groups and negates the need to remember individual IP addresses or domain names. 

Let’s create our inventory, but before doing so we need to create a new directory to house our Ansible logic. Anywhere is fine, but I use my home directory.

<pre>
mkdir ~/apps
</pre>

Create a new plain text file called `hosts` in the new directory, with the following contents:

<pre>
[production]
201.23.11.123
201.23.11.124
201.23.11.125
</pre>

The first line indicates the group name and the lines that follow are our hosts. Multiple groups can be created using the `[group name]` syntax and hosts can belong to multiple groups. For example:
<pre>
[staging]
201.23.11.120

[production]
201.23.11.123
201.23.11.124
201.23.11.125

[db]
201.23.11.129
</pre>

Now we need to instruct Ansible where our inventory file is located. Create a new file called `ansible.cfg` with the following contents.

<pre>
[defaults]
inventory = hosts
</pre>

# Running Commands

With our inventory file populated we can start running basic commands on the hosts, but first let’s briefly look at [modules](https://docs.ansible.com/ansible/latest/user_guide/modules.html) . Modules are small plugins that are executed on the host and allow you to interact with the remote system, as if you were logged in via SSH. Common modules include: apt, service, file and lineinfile, but Ansible ships with hundreds of [core modules](https://docs.ansible.com/ansible/latest/modules/list_of_all_modules.html), all of which are maintained by the core development team. Modules greatly simplify the process of running commands on your remote systems, and cut down the need to manually write shell or bash scripts. Generally, most unix commands have an associated module and if not, someone else has probably created one.

Let’s take a look at the ping module, which ensures we can connect to our hosts:
<pre> 
ansible production -m ping -u root
</pre>


# Playbooks

[Playbooks](https://docs.ansible.com/ansible/latest/user_guide/playbooks.html) allow you to chain commands together, essentially creating a blueprint or set of procedual instructions. Ansible will execute the playbook in sequence and ensure the state of each command is as desired before moving onto the next. This is what makes Ansible idempotent. If you cancel the playbook execution partway through and restart it later, only the commands that haven’t completed previously will execute.


# Organization

Let’s take a look at how our playbook is organized.
<pre>

├── ansible.cfg
├── hosts
├── provision.yml
└── roles
  └── apps
    ├── handlers
      └── main.yml
    ├── tasks
      └── main.yml
</pre>

The `hosts` and `ansible.cfg` files should be familiar, but let’s take a look at the `provision.yml` file.

<pre> 
---
- hosts: production
  become: yes
  remote_user: root
  roles: 
     - apps 
</pre>

let's have a look for ansible [Privilege Escalation](https://docs.ansible.com/ansible/latest/user_guide/become.html) 

Get free ebook [mastering-ansible](https://www.ansible.com/resources/ebooks/mastering-ansible)

Get free resource [awesome-ansible] (https://github.com/jdauphant/awesome-ansible)
