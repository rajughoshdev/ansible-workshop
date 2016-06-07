# Ansible nginx server blocks(virtual host) roles 

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

## Setting up your hosts file

You need to modify your host machine's hosts file for Linux/Mac: `sudo vim /etc/hosts`; adding the below:

    192.168.88.100 rajudemo.com
    192.168.88.100 rajutest.com

After configuring, you can visit http://rajudemo.com and http://rajutest.com  in a browser, then you'll see the sucessfull page. 
