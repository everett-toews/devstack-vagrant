# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  ## Box config

  config.vm.box = "ubuntu/trusty64"
  config.vm.provider "virtualbox" do |v|
    v.name = "devstack-txlf"
    v.memory = 4096
    v.cpus = 2
  end

  ## Network config

  config.vm.network :forwarded_port, guest: 80,   host: 8000, auto_correct: true
  config.vm.network :private_network, ip: "192.168.22.10"

  ## Provision config

  config.vm.provision :shell, path: "devstack.sh", privileged: false
end
