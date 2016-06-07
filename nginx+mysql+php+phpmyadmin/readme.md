# Ansible roles for  Nginx, Mysql, PHP & Phpmyadmin.

## Requirements

[Vagrant](https://www.vagrantup.com) and [VirtualBox](https://www.virtualbox.org) or (other VM provider like [VmWare](https://www.vmware.com) should be used to quickly build or construct a virtual servers and for installing Nginx, Mysql, PHP & Phpmyadmin using the [Ansible](http://www.ansible.com/) provisioner.

## Getting Started

There is a file name `Vagrantfile` which will tells to Vagrant how to set up your virtual machine in VirtualBox.

To run the vagrant file, you need to have done the following:

  1. Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
  2. Install [Vagrant](https://www.vagrantup.com/downloads.html)
  3. Install [Ansible](http://docs.ansible.com/intro_installation.html)

Once all of that is done, you can simply type in `vagrant up`, and Vagrant will create a new VM, install the base box, and configure it.

Once the new VM is up and running (after `vagrant up` is complete and you're back at the command prompt), you can log into it via SSH if you'd like by typing in `vagrant ssh`. Otherwise, the next steps are below.

## Setting up your hosts file

You need to modify your host machine's hosts file for Linux/Mac: `sudo vim /etc/hosts`; adding the line below:

    192.168.99.100  yourhostname or yourdomainname.com

(Where `yourhostname.com or yourdomainname.com`) is the hostname you have configured in the `Vagrantfile`).

After configuring, you can visit http://192.168.99.100/ or http://yourhostname/ or  http://yourdomainname.com or  in a browser, then you'll see the Apache 'It works!' page.

If you'd like additional assistance editing your hosts file, please read [How do I modify my hosts file?](http://www.rackspace.com/knowledge_center/article/how-do-i-modify-my-hosts-file) from Rackspace.

