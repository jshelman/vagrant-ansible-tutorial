# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "precise32"
  config.vm.box_url = "http://files.vagrantup.com/precise32.box"

  config.vm.define :db do |db|
    db.vm.network :private_network, ip: "192.168.100.20"
    db.vm.provider :virtualbox do |vb|
      vb.name = "db"
      vb.customize ["modifyvm", :id, "--memory", "512"]
    end
  end
  
  config.vm.define :web do |web|
    web.vm.network :private_network, ip: "192.168.100.10"
	web.vm.forward_port 80, 8080
    web.vm.provider :virtualbox do |vb|
      vb.name = "web"
      vb.customize ["modifyvm", :id, "--memory", "512"]
    end
  end
end
