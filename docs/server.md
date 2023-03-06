# Server Guide

## Ansible

Ansible is an open source automation platform used to manage the state
and configuration of machines.

### Vagrant

The Vagrant utility is used to setup a local workstation supports a command
to re-run the provisioning that is performed at the end of the `vagrant up`
process.

The `vagrant provision` command can be run again and again to apply the current
Ansible configurations for the ansible/local.yml playbook to the local Vagrant
machine.

To troubleshoot the application of this configuration, it is recommended that
you use the `vagrant provision --debug` command.

### Idempotency

It is possible to ensure that Ansible applies changes the virtual machine in an
idempotent manner. Idempotent is a term used in math and computer science that
describes a quality of an expression as having the same outcome no matter how
many times you execute the instruction.

Ansible is being used to log into the server and ensure that certain services
are installed, and configured a certain way. When running an Ansible playbook
against the server, if everything is installed and configured as expected, no
changes will be made. If something is not configured the same as before, then
the configuration will be modified to be as expected.

Because of this, it's possible to run a playbook over and over against a server,
and it will not cause issues or fail if the server is already setup. This is
nice because you can make configuration changes in the `/ansible` folder, then
run `vagrant provision` to ensure that the server
is properly configured.

### Ansible and Vagrant

* [Vagrant Provisioning - Ansible Intro](https://developer.hashicorp.com/vagrant/docs/provisioning/ansible_intro)

The [ansible/local.yml](ansible/local.yml) file is the playbook used to setup
the local Vagrant box.
