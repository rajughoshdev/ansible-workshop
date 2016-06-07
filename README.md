#Ansible Roles Example
####starting examples of th ansible playbook, features and how they work together.

Ansible is a radically simple IT automation engine that automates cloud provisioning, configuration management, application deployment, intra-service orchestration, and many other IT needs.

Being designed for multi-tier deployments since day one, Ansible models your IT infrastructure by describing how all of your systems inter-relate, rather than just managing one system at a time.

It uses no agents and no additional custom security infrastructure, so it's easy to deploy - and most importantly, it uses a very simple language (YAML, in the form of Ansible Playbooks) that allow you to describe your automation jobs in a way that approaches plain English.

On this page, we'll give you a really quick overview so you can see things in context. For more detail, hop over to [docs.ansible.com](https://docs.ansible.com)

#installing ansible on ubuntu
  <pre>
  sudo apt-get install software-properties-common
  
  sudo apt-add-repository ppa:ansible/ansible
  
  sudo apt-get update
  
  sudo apt-get install ansible
  </pre>
