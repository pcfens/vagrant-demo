# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "precise64-puppet"
  config.vm.box_url = "http://puppet-vagrant-boxes.puppetlabs.com/ubuntu-server-12042-x64-vbox4210.box"
  config.vm.provision "shell", path: "https://gist.github.com/pcfens/78198bd2da6f048bdb25/raw/9a7cee39b19050d1ec5e859b4761997ce83425c3/vagrant-prep.sh"

  config.vm.provision :puppet do |puppet|
    puppet.manifests_path = "puppet/manifests"
    puppet.module_path = "puppet/modules"
    puppet.manifest_file  = "site.pp"
    puppet.facter = {
      "vagrant" => "1"
    }
    puppet.options = [
      "--pluginsync"
    ]
  end
end
