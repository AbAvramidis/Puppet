# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  #config.vm.synced_folder "shared", "/tmp/shared"

  config.vm.provider "virtualbox" do |vb|
	vb.gui=false
	vb.memory = "2048"
	vb.cpus=2
  end
  
  config.vm.define "puppetMasterDG" do |masterDG|
		masterDG.vm.hostname = "masterMachineDG.qac.local"
		masterDG.vm.network "public_network", ip: "192.168.1.201"
		masterDG.vm.network "forwarded_port", guest: 80, host: 8080
		masterDG.vm.network "forwarded_port", guest: 8080, host: 9001

  end	
  
  config.vm.define "puppetAgentDG" do |agentDG|
		agentDG.vm.hostname = "agentMachineDG.qac.local"
		agentDG.vm.network "public_network", ip: "192.168.1.202"
		agentDG.vm.network "forwarded_port", guest: 80, host: 8081
		agentDG.vm.network "forwarded_port", guest: 8080, host: 9002
  end	

end
