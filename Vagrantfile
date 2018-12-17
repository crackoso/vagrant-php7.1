# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/trusty64"

  # config.vm.network "private_network", ip: "192.168.100.100"

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # NOTE: This will enable public access to the opened port
  # Apache2 Server
  # Port 8080 in host machine forwards to port 80 in guest machine
  config.vm.network "forwarded_port", guest: 80, host: 8080

  # MySQL Server
  # Port 33060 in host machine forwards to port 3306 in guest machine
  config.vm.network "forwarded_port", guest: 3306, host: 33060

  # Files/folders permissions
  config.vm.synced_folder ".", "/vagrant", :mount_options => ["dmode=777","fmode=766"]

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
    vb.cpus = 1
  end

  config.ssh.insert_key = false

  config.vm.provision :shell, keep_color: true, path: "Vagrant.provision.sh"

end