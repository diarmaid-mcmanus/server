Vagrant.require_version ">= 1.7.0"

Vagrant.configure(2) do |config|
  # Config the VMs. disable shared folder.
  config.vm.box = "ubuntu/trusty64"
  config.vm.synced_folder ".","/vagrant", :disabled => true
  config.ssh.insert_key = false

  # provision logging server, customise cores and ram
  config.vm.define "logging" do |server|
    server.vm.hostname = "logging"
    server.vm.network :private_network, ip: "10.10.1.249"

    server.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--memory", "2048" ]
      vb.customize ["modifyvm", :id, "--cpus", "2" ]
    end
  end

  config.vm.define "staticweb" do |server|
    server.vm.hostname = "staticweb"
    server.vm.network :private_network, ip: "10.10.1.11"
  end

  config.vm.define "loadbalancer" do |server|
    server.vm.hostname = "loadbalancer"
    server.vm.network :private_network, ip: "10.10.1.10"
    server.vm.network :forwarded_port, guest: 80, host: 80
    server.vm.network :forwarded_port, guest: 443, host: 443
  end

  config.vm.provider :virtualbox do |vb|
    vb.gui = false

    vb.customize [ "modifyvm", :id, "--memory", "512" ]
    vb.customize [ "modifyvm", :id, "--natdnshostresolver1", "on" ]
  end

#  config.vm.provision "ansible" do |ansible|
#    ansible.playbook = "main.yml"
#  end
end
