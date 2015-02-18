# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.ssh.insert_key = false

  config.vm.box = "ubuntu/trusty64"

  config.vm.define "docker" do |config|
    config.vm.hostname = "docker"

    config.vm.provider "virtualbox" do |vb|
      # vb.cpus = 4
      vb.memory = 512
    end

    config.vm.network "forwarded_port", guest: 2375, host: 2375, auto_correct: true
    config.vm.network "private_network", ip: "10.0.0.2"
    config.vm.synced_folder ENV['HOME'], ENV['HOME'], id: "home", :nfs => true, :mount_options => ['nolock,vers=3,udp']

    config.vm.provision "docker"
    config.vm.provision "shell", inline: "cp /vagrant/etc/default/docker /etc/default/docker", privileged: true
    config.vm.provision "shell", inline: "service docker restart", privileged: true
  end
end
