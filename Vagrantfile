# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|


  config.vm.provision "file", source: "./vagrant.pub", destination: "~/.ssh/key.pub"
  config.vm.provision "shell", inline: <<-SHELL
    cat /home/vagrant/.ssh/key.pub >> /home/vagrant/.ssh/authorized_keys
  SHELL

  (0..3).each do |i|
    config.vm.disk :disk, size: "1GB", name: "minio-#{i}"
  end


  config.vm.define "bigd-01" do |node1|
    node1.vm.box = "almalinux/8"
    node1.vm.hostname = 'bigd-01.trialogic.hr'
    node1.vm.boot_timeout = 500

    node1.ssh.insert_key = false
    node1.ssh.username = "vagrant"
    # node1.ssh.private_key_path = "vagrant"

    node1.vm.network "private_network", ip: "10.0.0.100"
    # node1.vm.network :forwarded_port, guest: 22, host: 3220

    node1.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--memory", 6000]
      v.customize ["modifyvm", :id, "--name", "bigd-01.trialogic.hr"]
      v.customize ["modifyvm", :id, "--cpus", 2]
    end
  end

  config.vm.define "bigd-02" do |node1|
    node1.vm.box = "almalinux/8"
    node1.vm.hostname = 'bigd-02.trialogic.hr'
    node1.vm.boot_timeout = 500

    node1.ssh.insert_key = false
    node1.ssh.username = "vagrant"
    # node1.ssh.private_key_path = "vagrant"

    node1.vm.network "private_network", ip: "10.0.0.101"
    # node1.vm.network :forwarded_port, guest: 22, host: 3220

    node1.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--memory", 6000]
      v.customize ["modifyvm", :id, "--name", "bigd-02.trialogic.hr"]
      v.customize ["modifyvm", :id, "--cpus", 2]
    end
  end

  config.vm.define "bigd-03" do |node1|
    node1.vm.box = "almalinux/8"
    node1.vm.hostname = 'bigd-03.trialogic.hr'
    node1.vm.boot_timeout = 500

    node1.ssh.insert_key = false
    node1.ssh.username = "vagrant"
    # node1.ssh.private_key_path = "vagrant"

    node1.vm.network "private_network", ip: "10.0.0.102"
    # node1.vm.network :forwarded_port, guest: 22, host: 3220

    node1.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--memory", 6000]
      v.customize ["modifyvm", :id, "--name", "bigd-03.trialogic.hr"]
      v.customize ["modifyvm", :id, "--cpus", 2]
    end
  end

end
