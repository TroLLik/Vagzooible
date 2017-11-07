# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/trusty64"
  config.vm.network "public_network"
  config.vm.hostname = "zoo-test"

  config.vm.provider "virtualbox" do |vb|
    vb.gui = true
    vb.memory = "512"
    vb.cpus = 1
  end

  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get upgrade -y
    apt-get install -y htop mc vim bash-completion aptitude
  SHELL
  
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "provisioning/tasks/main.yml"
  end

end
