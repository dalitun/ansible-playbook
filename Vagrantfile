# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    ############################################################
    # Create repertoire VM master1
    ############################################################
    config.vm.define "master1" do |master1|
        #master1.vm.box = "ubuntu/trusty64"
        #master1.vm.box = "bento/centos-7.2"
        #master1.vm.box =  "bento/centos-6.7"
        #master1.vm.box = "debian/jessie64"
        master1.vm.box = "ubuntu-14.04"
        master1.vm.box_url = "http://127.0.0.1/ubuntu-14.04.box"


        master1.vm.hostname = "master1"
        master1.vm.network :private_network, ip: "10.0.1.2"
        master1.vm.provider :virtualbox do |vb|
          vb.customize ["modifyvm", :id, "--memory", "1024"]
          vb.customize ["modifyvm", :id, "--cpus", "1"]
        end

      config.vm.provision "ansible" do |ansible|
      ansible.playbook = "db.yml"
      #ansible.extra_vars = "group_vars/db1.yml"

      end


    end

    ############################################################
    # Create repertoire VM master2
    ############################################################
    config.vm.define "master2" do |master2|
        #master2.vm.box = "ubuntu/trusty64"
        #master2.vm.box = "bento/centos-7.2"
        #master2.vm.box =  "bento/centos-6.7"
        #master2.vm.box = "debian/jessie64"
        master2.vm.box = "ubuntu-14.04"
        master2.vm.box_url = "http://127.0.0.1/ubuntu-14.04.box"
        master2.vm.hostname = "master2"
        master2.vm.network :private_network, ip: "10.0.1.3"
        master2.vm.provider :virtualbox do |vb|
          vb.customize ["modifyvm", :id, "--memory", "1024"]
          vb.customize ["modifyvm", :id, "--cpus", "1"]
        end

       config.vm.provision "ansible" do |ansible|
       ansible.playbook = "db.yml"
       #ansible.extra_vars = "group_vars/db2.yml"

       end

    end

end


