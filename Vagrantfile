# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure(2) do |config|
  config.vm.define  "concourse" do |host|
    host.vm.box = "ubuntu/xenial64"
    host.vm.hostname = "concourse"
    host.vm.network "private_network", ip: "192.168.51.96"
    host.vm.provision "shell", path: "./config/strap_env", privileged: false
    host.vm.provision :reload
    host.vm.provision "shell", path: "./config/install_concourse", privileged: false
    host.vm.network "forwarded_port", guest: 8080, host: 8080 
    host.vm.provider "virtualbox" do |vb|
      vb.memory = 4000 
    end
  end
end
