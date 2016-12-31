# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.ssh.insert_key = false
  config.vm.provision :ansible do |ansible|
    ansible.playbook = "./site.yml"
    #ansible.inventory_path = "./vagrant.py"
    ansible.verbose = true
  end
  config.ssh.private_key_path = ["/home/feuerrot/.ssh/vagrant", "~/.vagrant.d/insecure_private_key"]
  config.vm.provision "file", source: "/home/feuerrot/.ssh/vagrant.pub", destination: "~/.ssh/authorized_keys"

  config.vm.define "default" do |default|
    default.vm.box = "debian/jessie64"
  end
end
