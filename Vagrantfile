# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"

  config.vm.provider "virtualbox" do |v|
      v.memory = 2048
  end

  config.vm.network "forwarded_port", guest: 3000, host: 3000
  config.vm.network "forwarded_port", guest: 5858, host: 5858
  config.vm.network "forwarded_port", guest: 8080, host: 8080

  # Had to run as sudo to get some ports listening :(

  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y git tree htop
    curl https://install.meteor.com/ | sh
  SHELL
end
