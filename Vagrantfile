# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  #config.vm.synced_folder "shared", "/tmp/shared"

  config.vm.provider "virtualbox" do |vb|
	vb.gui=false
	vb.memory = "2048"
	vb.cpus=1
  end
  
  config.vm.define "puppetMasterDG" do |masterDG|
		masterDG.vm.hostname = "masterpuppet.local"
		masterDG.vm.network "public_network", ip: "10.0.10.10"
		masterDG.vm.network "forwarded_port", guest: 80, host: 8080
		masterDG.vm.network "forwarded_port", guest:9000, host:9002
  end	
  
  config.vm.define "puppetAgentDG" do |agentDG|
		agentDG.vm.hostname = "agentpuppet.local"
		agentDG.vm.network "public_network", ip: "10.0.10.11"
		agentDG.vm.network "forwarded_port", guest: 80, host: 8081
		agentDG.vm.network "forwarded_port", guest:9000, host:9003
  end	

end
