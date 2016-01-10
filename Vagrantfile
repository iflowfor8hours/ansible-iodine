# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"

  config.vm.define "iodine" do |iodine|
  end

  config.vm.hostname = 'iodine.172.19.22.23.xip.io'
  config.vm.network 'private_network', ip: '172.19.22.23'

  config.vm.provision :ansible do |ansible|
    ansible.playbook = 'test.yml'
#    ansible.verbose = 'vvvv'
  end

end
