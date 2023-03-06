# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.

# See https://developer.hashicorp.com/vagrant/docs for Vagrant online
# documentation

ANSIBLE_PATH = __dir__ + '/ansible' # absolute path to Ansible directory

# Set memory for all Docker Engines (guest machines)
GUEST_MEMORY = '2048' # recommended values - 1024, 2048, 4096, 8192

# Ubuntu 22.04 LTS (Jammy Jellyfish)
# Other images available for reference at https://app.vagrantup.com/boxes/search
GUEST_BOX = "ubuntu/jammy64"

Vagrant.configure("2") do |config|

  config.vm.define "docker", primary: true do |docker|
    docker.vm.box = GUEST_BOX
    docker.vm.hostname = 'docker'

    # Create a private network, which allows host-only access to the machine
    # using a specific IP.
    docker.vm.network :private_network, ip: '192.168.50.2'

    # Create a forwarded port mapping which allows access to a specific port
    # within the machine from a port on the host machine. In the example below,
    # accessing "localhost:8080" will access port 80 on the guest machine.
    # docker1.vm.network "forwarded_port", guest: 80, host: 2600, auto_correct: true

    # Create a public network, which generally matched to bridged network.
    # Bridged networks make the machine appear as another physical device on
    # your network.
    # docker1.vm.network "public_network"

    # Create synced folder between this repositories 'app' folder and the
    # '/home/ubuntu/app' directory within the virtual machine
    # docker1.vm.synced_folder "app", "/home/ubuntu/app"

    # NFS setup is recommended for efficient syncing. Requires private network config mentioned above.
    # docker1.vm.synced_folder "app", "/home/ubuntu/app", type: 'nfs'

    # By default Vagrant creates a /vagrant folder. This disables the default synced folder
    docker.vm.synced_folder '.', '/vagrant', disabled: true

    # Provider-specific configuration so you can fine-tune various
    # backing providers for Vagrant. These expose provider-specific options.
    # View the documentation for the provider you are using for more
    # information on available options.
    docker.vm.provider "virtualbox" do |vb|
      # Display the VirtualBox GUI when booting the machine
      vb.gui = false

      # Customize the amount of memory on the VM:
      vb.memory = GUEST_MEMORY
    end

    # https://developer.hashicorp.com/vagrant/docs/provisioning/ansible
    docker.vm.provision 'ansible' do |ansible|
      ansible.playbook = File.join(ANSIBLE_PATH, 'local.yml')
    end
  end

  config.vm.define "docker2" do |docker2|
    docker2.vm.box = GUEST_BOX
    docker2.vm.hostname = 'docker2'
    docker2.vm.network :private_network, ip: '192.168.50.3'

    docker2.vm.synced_folder '.', '/vagrant', disabled: true
    docker2.vm.provider "virtualbox" do |vb|
      vb.gui = false
      vb.memory = GUEST_MEMORY
    end

    docker2.vm.provision 'ansible' do |ansible|
      ansible.playbook = File.join(ANSIBLE_PATH, 'local.yml')
    end
  end

end
