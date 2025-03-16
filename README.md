# My Ansible Playbooks
This repository contains my collection of Ansible Playbooks that I'm developing as part of automating my infrastructure 

# Setting up Ansible
## Setting up Ansible Control Node


## Setting up Ansible within Windows Subsystem for Linux (WSL)

Follow the instructions at this Microsoft article to guide you through the process - I've extracted the key steps here. 

Step 1 First time installation of the WSL requires running the folliwng command from within Powershell (when ran as an Adminstrator)

`wsl --install`

Make sure you restart your computer after installing WSL!!.

Step 2

`TBD`

Before launching Ubuntu, launch the WSL Settings so that you can set the ability to paste code using Ctrl-Shift-V.

Step x

After the set up process, you will find Ubuntu installed as an application. Launching Ubuntu, you will need to create a default username and password

Step x

Update the package manager, apt, caches. First run

`sudo su` in order to sign in as root

Then run:

`apt get update -y`

Step x - Installation of Ansible
There are two ways to get Ansible, the first (and method I used is to add Ansible to the PPA (I think this is basically adding a reference to the repository) - the other approach is into install Python PIP (python's package manager and have that install Ansible), I chose the former for two reasons, firstly, the guide I used (https://phoenixnap.com/kb/install-ansible-on-windows) on installing Ansible used this approach first, secondly, I like the idea of the OS package manager keeping everything up to date.

You first need to install a software package with:

`sudo apt install software-properties-common`

Then add Ansible

`sudo apt-add-repository ppa:ansible/ansible`

Now update the package manager with the latest data with:

`apt get update -y`

The command the installation of Ansible using:

`sudo apt install ansible -y`







# About the playbooks
The following subsections describe each of the playbooks

## Install Git
There are two variants to achieve this: 
* installGit_ubuntu - this is designed to use "apt" package manager to install the git client on Ubuntu-based machines.
* installGit_windows - this is designed to download and install the Git for Windows client.
