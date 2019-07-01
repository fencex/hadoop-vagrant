# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # All Vagrant configuration is done here. The most common configuration
  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "bento/centos-7.4"


  # Fixes changes from https://github.com/mitchellh/vagrant/pull/4707
  config.ssh.insert_key = false

  # The url from where the 'config.vm.box' box will be fetched if it
  # doesn't already exist on the user's system.

  # CentOS 7.0 x86_64
  #config.vm.box_url = "http://cloud.terry.im/vagrant/oraclelinux-7-x86_64.box"

  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", 1024] # RAM allocated to each VM
  end

  config.vm.provision :shell, :path => "bootstrap.sh"

  config.vm.define :node01 do |node01|
    # uncomment the line below to set up the ambari dev environment
    # node01.vm.provision :shell, :path => "dev-bootstrap.sh"
    node01.vm.hostname = "node01"
    node01.vm.network :private_network, ip: "192.168.74.101"
    node01.vm.network :forwarded_port, guest: 8088, host:8188
  end

  config.vm.define :node02 do |node02|
    node02.vm.hostname = "node02"
    node02.vm.network :private_network, ip: "192.168.74.102"
    node02.vm.network :forwarded_port, guest: 8088, host:8288
  end

  config.vm.define :node03 do |node03|
    node03.vm.hostname = "node03"
    node03.vm.network :private_network, ip: "192.168.74.103"
  end

  config.vm.define :node04 do |node04|
    node04.vm.hostname = "node04"
    node04.vm.network :private_network, ip: "192.168.74.104"
    node04.vm.network :forwarded_port, guest: 50070, host:50470 
  end

  config.vm.define :node05 do |node05|
    node05.vm.hostname = "node05"
    node05.vm.network :private_network, ip: "192.168.74.105"
    node05.vm.network :forwarded_port, guest: 50070, host:50570 
  end

  config.vm.define :node06 do |node06|
    node06.vm.hostname = "node06"
    node06.vm.network :private_network, ip: "192.168.74.106"
  end

  config.vm.define :node07 do |node07|
    node07.vm.hostname = "node07"
    node07.vm.network :private_network, ip: "192.168.74.107"
  end

  config.vm.define :node08 do |node08|
    node08.vm.hostname = "node08"
    node08.vm.network :private_network, ip: "192.168.74.108"
  end

  config.vm.define :node09 do |node09|
    node09.vm.hostname = "node09"
    node09.vm.network :private_network, ip: "192.168.74.109"
  end

  config.vm.define :node10 do |node10|
    node10.vm.hostname = "node10"
    node10.vm.network :private_network, ip: "192.168.74.110"
  end





  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # config.vm.network :forwarded_port, guest: 80, host: 8080

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network :private_network, ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network :public_network

  # If true, then any SSH connections made will enable agent forwarding.
  # Default value: false
  # config.ssh.forward_agent = true

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  # config.vm.provider :virtualbox do |vb|
  #   # Don't boot with headless mode
  #   vb.gui = true
  #
  #   # Use VBoxManage to customize the VM. For example to change memory:
  #   vb.customize ["modifyvm", :id, "--memory", "1024"]
  # end
  #
  # View the documentation for the provider you're using for more
  # information on available options.

  # Enable provisioning with Puppet stand alone.  Puppet manifests
  # are contained in a directory path relative to this Vagrantfile.
  # You will need to create the manifests directory and a manifest in
  # the file precise32.pp in the manifests_path directory.
  #
  # An example Puppet manifest to provision the message of the day:
  #
  # # group { "puppet":
  # #   ensure => "present",
  # # }
  # #
  # # File { owner => 0, group => 0, mode => 0644 }
  # #
  # # file { '/etc/motd':
  # #   content => "Welcome to your Vagrant-built virtual machine!
  # #               Managed by Puppet.\n"
  # # }
  #
  # config.vm.provision :puppet do |puppet|
  #   puppet.manifests_path = "manifests"
  #   puppet.manifest_file  = "init.pp"
  # end

  # Enable provisioning with chef solo, specifying a cookbooks path, roles
  # path, and data_bags path (all relative to this Vagrantfile), and adding
  # some recipes and/or roles.
  #
  # config.vm.provision :chef_solo do |chef|
  #   chef.cookbooks_path = "../my-recipes/cookbooks"
  #   chef.roles_path = "../my-recipes/roles"
  #   chef.data_bags_path = "../my-recipes/data_bags"
  #   chef.add_recipe "mysql"
  #   chef.add_role "web"
  #
  #   # You may also specify custom JSON attributes:
  #   chef.json = { :mysql_password => "foo" }
  # end

  # Enable provisioning with chef server, specifying the chef server URL,
  # and the path to the validation key (relative to this Vagrantfile).
  #
  # The Opscode Platform uses HTTPS. Substitute your organization for
  # ORGNAME in the URL and validation key.
  #
  # If you have your own Chef Server, use the appropriate URL, which may be
  # HTTP instead of HTTPS depending on your configuration. Also change the
  # validation key to validation.pem.
  #
  # config.vm.provision :chef_client do |chef|
  #   chef.chef_server_url = "https://api.opscode.com/organizations/ORGNAME"
  #   chef.validation_key_path = "ORGNAME-validator.pem"
  # end
  #
  # If you're using the Opscode platform, your validator client is
  # ORGNAME-validator, replacing ORGNAME with your organization name.
  #
  # If you have your own Chef Server, the default validation client name is
  # chef-validator, unless you changed the configuration.
  #
  #   chef.validation_client_name = "ORGNAME-validator"
end
