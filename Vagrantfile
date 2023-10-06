# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
  #=============#
  # deploy  Node #
  #=============#

    config.vm.define "deploy-playcekube" do |cfg|
      cfg.vm.box = "ubuntu/jammy64"
      cfg.vm.provider "virtualbox" do |vb|
        vb.name = "deploy-playcekube"
        vb.cpus = 8
        vb.memory = 16384
        vb.customize ["modifyvm", :id, "--groups", "/playcekube"]
      end
      cfg.vm.host_name = "deploy"
      cfg.disksize.size = '500GB'
      cfg.vm.network "public_network", ip: "192.168.25.99", netmask: "255.255.0.0"
     # cfg.vm.network "forwarded_port", guest: 22, host: 25022, auto_correct: true, id: "ssh"
     # cfg.vm.network "forwarded_port", guest: 80, host: 25080, auto_correct: true, id: "ssh"
      cfg.vm.synced_folder "../data", "/vagrant", disabled: true 

    end
  #=============#
  # Master Node #
  #=============#


    config.vm.define "master-playcekube" do |cfg|
      cfg.vm.box = "ubuntu/jammy64"
      cfg.vm.provider "virtualbox" do |vb|
        vb.name = "master-playcekube"
        vb.cpus = 8
        vb.memory = 16384
        vb.customize ["modifyvm", :id, "--groups", "/playcekube"]
      end
      cfg.vm.host_name = "master"
      cfg.disksize.size = '200GB'
      cfg.vm.network "public_network", ip: "192.168.25.100", netmask: "255.255.0.0"
      #cfg.vm.network "private_network", ip: "192.168.25.100", name: "vboxnet2"
      #cfg.vm.network "forwarded_port", guest: 22, host: 20022, auto_correct: true, id: "ssh"
     # cfg.vm.network "forwarded_port", guest: 80, host: 20080, auto_correct: true, id: "ssh"
      cfg.vm.synced_folder "../data", "/vagrant", disabled: true 

    end

  #==============#
  # Worker Nodes #
  #==============#

    config.vm.define "worker-playcekube" do |cfg|
      cfg.vm.box = "ubuntu/jammy64"
      cfg.vm.provider "virtualbox" do |vb|
        vb.name = "worker-playcekube"
        vb.cpus = 8
        vb.memory = 16384
        vb.customize ["modifyvm", :id, "--groups", "/playcekube"]
      end
      cfg.vm.host_name = "worker"
      cfg.disksize.size = '200GB'
      cfg.vm.network "public_network", ip: "192.168.25.101", netmask: "255.255.0.0"
      #cfg.vm.network "private_network", ip: "192.168.25.101", name: "vboxnet2"
      #cfg.vm.network "forwarded_port", guest: 22, host: 20122, auto_correct: true, id: "ssh"
     # cfg.vm.network "forwarded_port", guest: 80, host: 20180, auto_correct: true, id: "ssh"
      cfg.vm.synced_folder "../data", "/vagrant", disabled: true 

    end

end
