# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.ssh.username = "fed"
  config.ssh.password = ""

  config.vm.box = "fed.node.v6"
  config.vm.box_check_update = false
  config.vm.box_download_checksum = "9e4f896a5efd0da3fe357538f59e04edb9bc68306492cddd3262671a96f24386"
  config.vm.box_download_checksum_type = "sha256"
  config.vm.box_url = "http://localhost:8080/fed.node.v6.box"

  config.vm.network "forwarded_port", guest: 9010, host: 9010
  config.vm.network "forwarded_port", guest: 9011, host: 9011
  config.vm.network "forwarded_port", guest: 35729, host: 35729
  config.vm.network "forwarded_port", guest: 5858, host: 5858
  config.vm.network "forwarded_port", guest: 27017, host: 27017
  config.vm.network "forwarded_port", guest: 3306, host: 3306

  config.vm.post_up_message = "welcome to fed.dev"
  config.vm.synced_folder "./", "/home/fed/www"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = 2048
    vb.cpus = 4
  end

  config.vm.provision "shell", privileged: false, path: "bootstrap.sh"

end
