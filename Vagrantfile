# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.ssh.insert_key = false
  config.vm.provider "virtualbox" do |vb|
    vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    vb.customize ["modifyvm", :id, "--memory", "256"]
  end

  config.vm.define "service1" do |service|
    service.vm.hostname = "log-service1.dev"
    service.vm.box = "deb/wheezy-amd64"
    service.vm.network "private_network", ip: "192.168.60.4"
  end

  config.vm.define "service2" do |service|
    service.vm.hostname = "log-service2.dev"
    service.vm.box = "deb/wheezy-amd64"
    service.vm.network "private_network", ip: "192.168.60.5"
  end

  config.vm.define "elk" do |elk|
    elk.vm.hostname = "log-elk.dev"
    elk.vm.box = "deb/wheezy-amd64"
    elk.vm.network "private_network", ip: "192.168.60.6"
    config.vm.provider "virtualbox" do |vb|
      vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      vb.customize ["modifyvm", :id, "--memory", "1024"]
      vb.customize ["modifyvm", :id, "--cpus", "2"]
    end
  end

end
