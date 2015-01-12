# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://atlas.hashicorp.com/search.
  config.vm.box = 'ubuntu/trusty64'

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  # config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #
  #   # Customize the amount of memory on the VM:
  #   vb.memory = "1024"
  # end
  #
  # View the documentation for the provider you are using for more
  # information on available options.

  # Define a Vagrant Push strategy for pushing to Atlas. Other push strategies
  # such as FTP and Heroku are also available. See the documentation at
  # https://docs.vagrantup.com/v2/push/atlas.html for more information.
  # config.push.define "atlas" do |push|
  #   push.app = "YOUR_ATLAS_USERNAME/YOUR_APPLICATION_NAME"
  # end

  # Enable provisioning with a shell script. Additional provisioners such as
  # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
  # documentation for more information about their specific syntax and use.
  config.vm.provision :ansible do |ansible|
    ansible.playbook = 'role.yml'
    # pip install passlib && python -c "from passlib.hash import sha512_crypt; import getpass; print sha512_crypt.encrypt(getpass.getpass())"
    # your_password
    ansible.extra_vars = {
      user: {
        password: '$6$rounds=100000$DyBul1962v1jYEMp$gusMKnoORGlF.1d4nQsijXcH9JwGsi3e9m4F7qrR3Azj.v0fXpyJVrKeIP0cqg3rNe1vfRn0OYSkMCVwQ0s//.',
        ssh_key: 'ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCsNR7Iwc36JVXtNxh+CvG5oW4cFEe4PbmRJ/2XJWBxcjKZ43a9zJ2RzGGo/Uo4gk+Jr+qGPRWCjwIdVx4C+v/u7gLqsCRT/uNxmq63+AoFeKJo+YvHJ3sLxB/SkxgTgsDhEU7i9Y14CnAIzRq1GBFaJzWV+dj6tif4pDbhrsnzPYXUd/dKp7sAH/2WX50zH4qigvEl8PnqJxCc0nnnIhOqgY+T5craZRaLYAQGxVlapVCKT1YX94bL+aaWLvGTyW4JCp/jc3nN8ckY4w3Cu34mA/xP4+6N7+pKgPonzUq798ghxilDNX+s2xnUWIaJWwVNKBIqzLrhf31nPYnjGfpf leonel@smashingboxes.com'
      }
    }
  end
end
