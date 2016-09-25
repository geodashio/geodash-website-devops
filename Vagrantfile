# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.box = "bento/ubuntu-16.04"

  config.vm.network "forwarded_port", guest: 4000, host: 8000

  config.vm.synced_folder "~/workspaces/public/geodash.github.io.git", "/home/vagrant/geodash.github.io.git"

  config.vm.provider "virtualbox" do |vb|\
      vb.gui = true
      vb.cpus = 2
      vb.memory = 4096
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ansible/ubuntu_geodash_website.yml"
    ansible.host_key_checking = false
    ansible.verbose = "v"
    ansible.raw_arguments = []
  end

end
