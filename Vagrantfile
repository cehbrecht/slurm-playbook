# -*- mode: ruby -*-
# vi: set ft=ruby :

# This guide is optimized for Vagrant 1.7 and above.
Vagrant.require_version ">= 1.7.0"

Vagrant.configure("2") do |config|

#######################################
### slurm nodes  ######################
#######################################

  # Increased memory (default: 512) to resolve conda envs in jaspy (21/06/2019)
  config.vm.provider "virtualbox" do |vb|
    vb.customize ["modifyvm", :id, "--memory", "2048"]
    vb.customize ["modifyvm", :id, "--cpus", 2]
  end

  # Disable the new default behavior introduced in Vagrant 1.7, to
  # ensure that all Vagrant machines will use the same SSH key pair.
  # See https://github.com/mitchellh/vagrant/issues/5005
  config.ssh.insert_key = false
  config.ssh.private_key_path = '~/.vagrant.d/insecure_private_key'

  config.vm.define "slurmmaster" do |slurmmaster|
    slurmmaster.vm.box = "bento/centos-7"
    slurmmaster.vm.hostname = "slurmmaster.local"
    slurmmaster.vm.network "private_network", ip: "192.168.50.44"
    # slurmmaster.vm.provision 'ansible' do |ansible|
    #   ansible.playbook = 'playbook-single.yml'
    #   ansible.verbose = "v"
    #   ansible.host_key_checking = false
    # end
  end
  config.vm.define "slurmbatch1" do |slurmbatch1|
    slurmbatch1.vm.box = "bento/centos-7"
    slurmbatch1.vm.hostname = "slurmbatch1.local"
    slurmbatch1.vm.network "private_network", ip: "192.168.50.45"
    # slurmbatch1.vm.provision 'ansible' do |ansible|
    #   ansible.playbook = 'playbook-single.yml'
    #   ansible.verbose = "v"
    #   ansible.host_key_checking = false
    # end
  end
  config.vm.define "slurmbatch2" do |slurmbatch2|
    slurmbatch2.vm.box = "bento/centos-7"
    slurmbatch2.vm.hostname = "slurmbatch2.local"
    slurmbatch2.vm.network "private_network", ip: "192.168.50.46"
    # slurmbatch2.vm.provision 'ansible' do |ansible|
    #   ansible.playbook = 'playbook-single.yml'
    #   ansible.verbose = "v"
    #   ansible.host_key_checking = false
    # end
  end
end
