# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
# required_plugins = ["vagrant-hostsupdater", "vagrant-berkshelf"]
# required_plugins.each do |plugin|
#   exec "vagrant plugin install #{plugin}" unless Vagrant.has_plugin? has_plugin
# end

Vagrant.configure("2") do |config|

  config.vm.define "development" do |development|
    development.vm.box = "ubuntu/xenial64"
    ENV['LC_ALL']="en_US.UTF-8"
    ENV['LC_CTYPE']="en_US.UTF-8"
    development.vm.network "private_network", ip: "192.168.10.100"
    development.hostsupdater.aliases = ["development.local"]

    development.vm.synced_folder ".", "/app"

    development.vm.provision "chef_solo" do |chef|
      chef.add_recipe "python::default"
      chef.add_recipe "nginx::default"
    end
  end
end
