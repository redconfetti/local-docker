# Usage Guide

## Bring Up Docker Engines

From the root directory of this repository run `vagrant up` to setup the local
Ubuntu server configured in the Vagrantfile.

```shell
vagrant up docker
```

## Multi Machine Setup

By default we configure only a single Docker Engine machine as the primary
in the Vagrantfile.

We've left a second Docker Engine machine configuration in this file, but
commented out. Feel free to use this as a template to specify as many other
machines as you wish to setup under Virtualbox.

The second machine is named 'docker2' so bringing it up would require the
command `vagrant up docker2`. Other vagrant commands will also require that you
specify the guest machine (e.g. `vagrant status docker2`).

For more information see [Vagrant Docs - Multi-Machine]

[Vagrant Docs - Multi-Machine]: https://developer.hashicorp.com/vagrant/docs/multi-machine

## Vagrant

Here is a cheatsheet for all the Vagrant commands you can use to manage your
Docker Engine machine.

* `vagrant up` - starts and sets up the vagrant machine(s)
* `vagrant halt` - stops the vagrant machines
* `vagrant destroy` - stops and deletes all traces of the vagrant machines
* `vagrant reload` - stops and deletes the vagrant machines
* `vagrant ssh` - connects to a vagrant machine via Secure Shell
  (SSH)
* `vagrant status` - outputs status of a vagrant machine related to
  the application in the current directory
* `vagrant global-status` - outputs status of all vagrant machines that exist
* `vagrant provision` - runs the provisioning on the vagrant machine

For more commands run `vagrant --help`.

## Editor Config

Developers working on this code will need to download and install the
[Editor Config plugin](http://editorconfig.org/#download) for the text editor
you are using.

## Accessing Command Line Interface

If your application is a command line tool, use `vagrant ssh` to log into the
Vagrant box (virtual machine) as the `ubuntu` user.
