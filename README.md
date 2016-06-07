#Ansible Roles Example
####starting examples of th ansible playbook, features and how they work together.

Ansible is a radically simple IT automation engine that automates cloud provisioning, configuration management, application deployment, intra-service orchestration, and many other IT needs.

Being designed for multi-tier deployments since day one, Ansible models your IT infrastructure by describing how all of your systems inter-relate, rather than just managing one system at a time.

It uses no agents and no additional custom security infrastructure, so it's easy to deploy - and most importantly, it uses a very simple language (YAML, in the form of Ansible Playbooks) that allow you to describe your automation jobs in a way that approaches plain English.

On this page, we'll give you a really quick overview so you can see things in context. For more detail, hop over to [docs.ansible.com](https://docs.ansible.com)

## Requirements
[Vagrant](https://www.vagrantup.com) and [VirtualBox](https://www.virtualbox.org) or (other VM provider like [VmWare](https://www.vmware.com)) should be used to quickly build or construct a virtual servers and for installing Nginx, Mysql, PHP & Phpmyadmin using the [Ansible](http://www.ansible.com/) provisioner.

## Getting Started
There is a file name `Vagrantfile` which will tells to Vagrant how to set up your virtual machine in VirtualBox.

To run the vagrant file, you need to have done the following:

  1. Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
  2. Install [Vagrant](https://www.vagrantup.com/downloads.html)
  3. Install [Ansible](http://docs.ansible.com/intro_installation.html) or 
  <pre>
  sudo apt-get install software-properties-common

  sudo apt-add-repository ppa:ansible/ansible

  sudo apt-get update

  sudo apt-get install ansible
  </pre>

Once all of that is done, you can simply type in `vagrant up`, and Vagrant will create a new VM, install the base box, and configure it.

Once the new VM is up and running (after `vagrant up` is complete and you're back at the command prompt), you can log into it via SSH if you'd like by typing in `vagrant ssh`. Otherwise, the next steps are below.

