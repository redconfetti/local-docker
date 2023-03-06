# Usage Guide

## Bring Up Docker Engines

Two Docker Engine machines are configured under the Vagrantfile.

* docker
* docker2

You can bring these up independently like so:

```shell
# bring up first Docker Engine machine
vagrant up docker

# bring up second Docker Engine machine
vagrant up docker2
```

These machines are configured local to your host machine on the following
IP addresses:

* docker - 192.168.50.2
* docker2 - 192.268.50.3

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

For more commands run `vagrant --help`, or see [Vagrant Docs][].

[Vagrant Docs]: https://developer.hashicorp.com/vagrant/docs

### Multi Machine

Commands that refer to a Vagrant machine require that you specify the machine
by name. For example, to remove the second machine, you would need to run
`vagrant destroy docker2`.

For more information see [Vagrant Docs - Multi-Machine]

[Vagrant Docs - Multi-Machine]: https://developer.hashicorp.com/vagrant/docs/multi-machine
