DJA LEMP STACK
==============

This is a tutorial to setup DJA LEMP stack on your local computer, please follow below instruction.

----

## Requirement
- Virtual Box 
- Vagrant
- Your computer ( of course )


For windows users please install gitbash ( even better with [zsh](https://github.com/robbyrussell/oh-my-zsh) ), cygwin, or any unix based console to your machine. This is will make your life easier. Trust me.

-----
**Virtual Box**
Install virtual box ( This is the virtual machine host )
- [Mac OSX](http://download.virtualbox.org/virtualbox/5.1.12/VirtualBox-5.1.12-112440-OSX.dmg)
- [Windows](http://download.virtualbox.org/virtualbox/5.1.12/VirtualBox-5.1.12-112440-Win.exe)


**Vagrant**
Install vagrant ( we can invoke the VM spec with vagrant cli command )
- [Mac OSX](https://releases.hashicorp.com/vagrant/1.9.1/vagrant_1.9.1.dmg)
- [Windows](https://releases.hashicorp.com/vagrant/1.9.1/vagrant_1.9.1.msi)

**DJA Stack Repo**
[Download](https://github.com/anthonyguntur/djastack/archive/master.zip) our DJA stack repo and save that into any folder on your machine

## Folder Structure
Vagrantfile
> Virtual Machine configuration is here
Provision
:	setup.sh

> a bunch of bash script to build our stack
Public
> your project should be placed here and it will auto sync with your /var/www VM folder
:	index.php
:	info.php

nginx_conf
> a templates folder to create default nginx conf file
:	nginx_vhost 
	

## How to use
1. Go inside djastack folder
2. Run `vagrant up` wait until the provision is done
3. Open your browser and run `192.168.11.11` you should see index file
4. To stop the machine use `vagrant halt`
5. To destroy it use `vagrant destroy`
6. simple as that

For extra configuration please check [vagrant](https://www.vagrantup.com) official site

## Domain alias
**Windows users** 
Use your command prompt as administrator and go to `notepad C:\Windows\System32\Drivers\etc\hosts`
add `192.168.11.11 localhost` into a new line or with whatever name you come up with.

**Mac Users**
`sudo nano /etc/hosts` and add this new line `192.168.11.11 localhost`

Note: flush your dns cache if it doesn't work.

## SQL Client

Below is the settings for sequel pro, you can use it for any mysql client tools.

Use SSH tab

MySQL Host: `127.0.0.1`
Username: `root`
Password: `root`

SSH Host: `198.168.11.11`
SSH User: `vagrant`
SSH Password: `vagrant`

Test the connection and save it if it successful

-----
>DJA Stack version 1.0