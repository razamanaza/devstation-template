# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "peru/ubuntu-18.04-desktop-amd64"
  config.vm.box_check_update = false
  config.vm.hostname = "devstation.loc"
  config.vm.network "private_network", type: "dhcp"
  config.vm.synced_folder "data", "/vagrant", 
    create: true, type: "virtualbox"

  config.vm.provider "virtualbox" do |vb|
    vb.gui = true
    vb.memory = "3072"
  end

  config.vm.provision "ansible_local" do |ansible|
    ansible.become = true
    ansible.playbook = "playbook.yml"
    ansible.install = true
  end

end
