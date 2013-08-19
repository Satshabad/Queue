# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.hostname = "dev"

  config.vm.box = 'ubuntu-12.04-x86_64'
  config.vm.box_url = 'http://files.vagrantup.com/precise64.box'

  config.vm.synced_folder "api", "/srv/www/queue/api"
  config.vm.synced_folder "website/app", "/srv/www/queue/site"

  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    vb.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
  end

  config.vm.network :private_network, ip: "192.168.19.2"
  config.vm.network :forwarded_port, guest: 80, host: 8000


end
