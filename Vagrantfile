# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure(2) do |config|

  config.vm.define "hadoopmaster" do |controller_vagrant|
  controller_vagrant.vm.box = "ubuntu/trusty64"
  controller_vagrant.vm.network "public_network", ip: "192.168.1.78"
  controller_vagrant.vm.hostname = "hadoopmaster"
  controller_vagrant.vm.network "forwarded_port", guest: 50070, host: 8080
  controller_vagrant.vm.provider "virtualbox" do |v|
    v.memory = 1600
  end
    controller_vagrant.vm.provision "ansible" do |ansible|
      ansible.playbook = "hadoopmaster.yml"
      ansible.verbose = "v"
    end
  end

  config.vm.define "hadoopslave" do |compute_vagrant|
  compute_vagrant.vm.box = "ubuntu/trusty64"
  compute_vagrant.vm.hostname = "hadoopslave"
  compute_vagrant.vm.network "public_network", ip: "192.168.1.79"
  compute_vagrant.vm.provider "virtualbox" do |v|
    v.memory = 1600
  end
    compute_vagrant.vm.provision "ansible" do |ansible|
      ansible.playbook = "hadoopslave.yml"
      ansible.verbose = "v"
    end
  end
end

