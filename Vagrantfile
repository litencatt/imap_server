# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant::DEFAULT_SERVER_URL.replace('https://vagrantcloud.com')

Vagrant.configure("2") do |config|
  config.vm.box = "bento/centos-7.4"
  config.vm.synced_folder ".", "/vagrant", type: "rsync", rsync__exclude: [
    ".git/",
    "vendor/bundle"
  ]

  config.vm.define :imap do |c|
    c.vm.network :private_network, ip: '192.168.33.10'
    c.vm.hostname = :imap01
    config.vm.provider :virtualbox do |vbox|
      vbox.customize ["modifyvm", :id, "--memory", 512]
      vbox.customize ["modifyvm", :id, "--cpus", 2]
    end
  end

  config.vm.define :rainloop do |c|
    c.vm.network :private_network, ip: '192.168.33.11'
    c.vm.hostname = :client
    config.vm.provider :virtualbox do |vbox|
      vbox.customize ["modifyvm", :id, "--memory", 512]
      vbox.customize ["modifyvm", :id, "--cpus", 2]
    end
  end

  config.vm.define :roundcube do |c|
    c.vm.network :private_network, ip: '192.168.33.12'
    c.vm.hostname = :client
    config.vm.provider :virtualbox do |vbox|
      vbox.customize ["modifyvm", :id, "--memory", 512]
      vbox.customize ["modifyvm", :id, "--cpus", 2]
    end
  end
end
