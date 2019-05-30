# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "ubuntu/xenial64"

  # Configure virtual machine specs. Keep it simple, single user.
  config.vm.provider :virtualbox do |p|
    p.customize ["modifyvm", :id, "--memory", 8192]
    p.customize ["modifyvm", :id, "--cpus", 2]
  end

  # Configure port forwarding to TF web UI
  config.vm.network "forwarded_port", guest: 8143, host: 8143

  # Configure a synced folder between HOST and GUEST
  config.vm.synced_folder ".", "/vagrant", id: "vagrant-root", :mount_options => ["dmode=777","fmode=777"]

  # Configure disk size to 50G
  config.disksize.size = '50GB'

  # Config hostname and IP address so entry can be added to HOSTS file
  config.vm.hostname = "vagrant"

  # Install NTP
  config.vm.provision "shell", inline: "sudo apt-get -y install ntp"

end
