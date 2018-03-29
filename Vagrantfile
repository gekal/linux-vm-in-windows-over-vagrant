# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|

  # Every Vagrant development environment requires a box.
  config.vm.box = "centos/7"

  # Disable automatic box update checking.
  config.vm.box_check_update = true

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine and only allow access
  # via 127.0.0.1 to disable public access
  config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"
  config.vm.network "forwarded_port", guest: 22, host: 10022, host_ip: "127.0.0.1"

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  config.vm.network "private_network", ip: "192.168.21.1"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  config.vm.synced_folder ".", "/vagrant", type: "virtualbox"

  # Define the name of hostname
  config.vm.hostname = "myhost"

  config.vm.provider "virtualbox" do |vb|
    # Virtual box machine name
    vb.name = "centos7"

    # Define the groou of virtual box
    vb.customize [
      "modifyvm", :id,
      "--groups", "/centos"
    ]

    # Display the VirtualBox GUI when booting the machine
    vb.gui = false

    # Customize the amount of memory on the VM:
    vb.memory = "1024"
  end

  # Add the proxy config if you need.
  if Vagrant.has_plugin?("vagrant-proxyconf")
    # config.proxy.http     = "http://host:port/"
    # config.proxy.https    = "http://host:port/"
    # config.proxy.no_proxy = "localhost,127.0.0.1"
  end
end
