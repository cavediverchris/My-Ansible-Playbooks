# My Ansible Playbooks

This repository contains my collection of Ansible Playbooks that I'm developing as part of automating my infrastructure 

# Setting up Ansible

## Setting up Ansible Control Node

What is the control node? The control node is like the master / head / server / boss. This is what has all the scripts that define the configurations (defined as playbooks) for all your clients or "hosts". This then talks to a 'local' client installation of Ansible on the host in order to execute those commands to configure the host as specified.

At the moment, I'm using the same physical machine (a Windows-based computer), that has Windows Subsystem for Linux (WSL) running, so the WSL contains Ubuntu so that is the "Control Node" and then the underlying Windows machine is one the hosts to be configured. Slightly Inception mind-bending at the moment! So I'm recording the process for doing this in the section "Setting up Ansible within Windows Subsystem for Linux".

## 



## Setting up Ansible within Windows Subsystem for Linux (WSL)

I've assembled this guide based on material from Jeff Geerling (https://www.youtube.com/watch?v=N7tgLVCXup4&t=2414s) and from the official Ansible documentation.

Follow the instructions at this Microsoft article to guide you through the process - I've extracted the key steps here. 

Step 1

First time installation of the WSL requires running the following command from within Powershell (when ran as an Adminstrator)

`wsl --install`

Make sure you restart your computer after installing WSL!!

Step 2

`TBD`

Before launching Ubuntu, launch the WSL Settings so that you can set the ability to paste code using Ctrl-Shift-V.

Step 3

After the set up process, you will find Ubuntu installed as an application. Launching Ubuntu, you will need to create a default username and password.

From this point on, this is now the typical setup of Ansible on an Ubuntu machine.  So continue according to [Setting up Ansible within Ubuntu](#setting-up-ansible-within-ubuntu). Once complete, return here.

Step 4 - Connecting Ansible to Windows

You've got WinRM and SSH as the two main options of getting commands from Ansible to be affected in Windows. This guide covers SSH for now.

TODO: Follow this guide: [GitHub - PowerShell/Win32-OpenSSH: Win32 port of OpenSSH](https://github.com/PowerShell/Win32-OpenSSH)



## Setting up Ansible within Ubuntu

This section describes how to setup Ansible within Ubuntu

Step 1

Update the package manager, apt, caches. First run

`sudo su` in order to sign in as root

Then run:

`apt get update -y`

Step 2 - Installation of Ansible
There are two ways to get Ansible, the first (and method I used is to add Ansible to the PPA (I think this is basically adding a reference to the repository) - the other approach is into install Python PIP (python's package manager and have that install Ansible), I chose the former for two reasons, firstly, the guide I used (https://phoenixnap.com/kb/install-ansible-on-windows) on installing Ansible used this approach first, secondly, I like the idea of the OS package manager keeping everything up to date.

You first need to install a software package with:

`apt install software-properties-common`

Then add Ansible

`apt-add-repository ppa:ansible/ansible`

Now update the package manager with the latest data with:

`apt get update -y`

The command the installation of Ansible using:

`apt install ansible -y`

If this is for a machine running WSL, then return to the [Setting Up Ansible within Windows using WSL](#Setting-up-Ansible-within-Windows-Subsystem-for-Linux-WSL).



# About the playbooks

The following subsections describe each of the playbooks

## Install Git

The purpose of this is to install the Git version control system on the host. Git is the primary version control system in use, then there is some very limited setup. There are two variants to achieve this: 

* installGit_ubuntu - this is designed to use "apt" package manager to install the git client on Ubuntu-based machines.
* installGit_windows - this is designed to download and install the Git for Windows client.
