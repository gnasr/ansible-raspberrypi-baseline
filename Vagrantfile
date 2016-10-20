# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  if Vagrant.has_plugin?("vagrant-cachier")
    # add config here
    config.cache.scope = :box
  end

  # get current image from https://github.com/ffuenf/vagrant-boxes
  config.vm.box = "https://s3.eu-central-1.amazonaws.com/ffuenf-vagrantboxes/debian/debian-8.6.0-amd64_virtualbox.box"

  config.vm.provider "virtualbox" do |v|
    v.gui = false
    v.name = "ansible-raspberrypi-baseline"

    v.customize ["modifyvm", :id, "--memory", "512"]
    v.customize ["modifyvm", :id, "--cpus", "1"]
    v.customize ["modifyvm", :id, "--ioapic", "on"]
  end

  config.vm.provision "shell", path: "bootstrap.sh"
end
