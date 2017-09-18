# -*- mode: ruby -*-
# vi: set ft=ruby :

VM_NODE_NAME = "registry"
VM_NODE_NUM = 1
VM_NODE_MEM = 1

Vagrant.configure("2") do |config|
  (1..VM_NODE_NUM).to_a.each do |n|
    config.vm.define "#{VM_NODE_NAME}#{n}" do |ubuntu|
      ubuntu.vm.box = "ubuntu/xenial64"
      ubuntu.vm.hostname = "#{VM_NODE_NAME}#{n}"
      ubuntu.vm.network "public_network"
      # config.vm.network "private_network", type: "dhcp"
      ubuntu.vm.synced_folder "./", "/vagrant", disabled:true
      ubuntu.vm.provider "virtualbox" do |vb|
        vb.name = "#{VM_NODE_NAME}#{n}"
        vb.cpus = 1
        vb.memory = VM_NODE_MEM*1024
      end
    end
  end
end
