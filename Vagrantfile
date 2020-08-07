# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|

  config.vm.define "packer" do |packer|
    packer.vm.box = "ubuntu/bionic64"
    packer.vm.network "private_network", ip: "192.168.200.200"
    packer.vm.provision "shell", path: "provision.sh", privileged: false
    packer.vm.synced_folder "packer", "/home/ubuntu/packer"
  end

end
