# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|

  config.vm.define "net1" do | p |
   p.vm.box = "ubuntu/jammy64"
   p.vm.host_name = "net1"
   p.vm.network  "public_network", bridge: "wlp6s0"

       p.vm.provider :virtualbox do |res|

          res.customize ["modifyvm", :id, "--cpus", "1"]
          res.customize ["modifyvm", :id, "--memory", "512"]
       end

  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "task3.yml"
    #ansible.compatibility_mode = "2.0"
    #ansible.verbose = "vvv"
  end

  
end
