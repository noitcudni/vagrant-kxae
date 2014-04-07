# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  
  Vagrant.require_version ">= 1.4.3"

  config.vm.define :kxae do | kxae |
    kxae.vm.box = "kxae"
    
    # Create a private network
    kxae.vm.network :forwarded_port, guest: 8080, host: 8080
    kxae.vm.network :private_network, ip: "192.168.1.2"
    kxae.vm.hostname = "kxae"
    
    config.vm.provider :virtualbox do |vb|
      vb.name = "kxae"
      vb.customize ["modifyvm", :id, "--memory", "5024"]
      vb.customize ["modifyvm", :id, "--cpus", "2"]
    end
  end
end
