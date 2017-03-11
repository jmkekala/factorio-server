# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "jmkekala/centos73"
  config.vm.synced_folder '.', '/vagrant', disabled: true
  
  config.vm.hostname = "factorio-dev"

  config.vm.provider "hyperv" do |hv|
    hv.vmname = "factorio-dev"
    hv.cpus = 2
    hv.memory = 1024
    hv.differencing_disk=true
  end

  config.vm.provision "shell", inline: <<-SHELL
  SHELL
end

