# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.define "ci", autostart: true do |ci|
    ci.vm.network "public_network", bridge: "en1: Wi-Fi (AirPort)"
    ci.vm.box = "ubuntu/trusty64"
    ci.vm.hostname = "ci"
    ci.vm.provision "ansible" do |ansible|
      ansible.playbook = "ci.yml"
      ansible.groups = {
        "manager" => ["ci"],
        "worker" => ["worker1","worker2"]
      }
    end
    ci.vm.provider :virtualbox do |v|
      v.memory = 6000
      v.cpus = 2
    end
  end

end
