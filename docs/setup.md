# Setup Guide

## Package Managers

Download and install the package manager listed below for your operating system.

* Mac OSX - Install [Homebrew](http://brew.sh/)
* Windows - Install [Chocolatey](https://chocolatey.org/)
* Ubuntu / Debian - No action necessary. Commands below make use of
[Advanced Packaging Tool (APT)](https://en.wikipedia.org/wiki/Advanced_Packaging_Tool)
to install needed software.

### VirtualBox

VirtualBox is an application that sets up and manages virtual machines running
on your workstation.

```shell
# Windows
choco install virtualbox

# Mac
brew install --cask virtualbox

# Ubuntu
sudo apt-get install virtualbox
```

Alternatively you can download VirtualBox from the official
[download page](https://www.virtualbox.org/wiki/Downloads).

## Vagrant

Vagrant is a utility that makes it possible to automate the creation and setup
of a virtual machine (the Vagrant box).

```shell
# Windows
choco install vagrant

# Mac
brew install vagrant

# Ubuntu
sudo apt-get install vagrant
```

Alternatively you can download and install Vagrant from the official
[download page](https://www.vagrantup.com/downloads.html).

Windows or Mac users may optionally install
[VagrantManager](http://vagrantmanager.com/) to manage Vagrant boxes (virtual
machines) using a GUI application.

```shell
# Windows
choco install vagrant-manager

# Mac
brew install --cask vagrant-manager
```

## Ansible

Ansible is a utility used to manage the software and configurations within one
or more machines.

```shell
# Mac
brew install ansible

# Windows
choco install pip
pip install ansible

# Ubuntu
sudo apt-get install software-properties-common
sudo apt-add-repository ppa:ansible/ansible
sudo apt-get update
sudo apt-get install ansible
```

Alternatively you can download and install Ansible from the official
[download page](http://docs.ansible.com/ansible/intro_installation.html).

## Editor Config

Developers working on this code will need to download and install the
[Editor Config plugin](http://editorconfig.org/#download) for the text editor
you are using.

## See Usage

After this is completed, refer to the [Usage Guide](usage.md) for further
orientation.
