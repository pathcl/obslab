Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.synced_folder '.', '/vagrant', disabled: true
  config.vm.network "forwarded_port", guest: 9090, host: 9090, host_ip: "192.168.1.33"
  config.vm.network "forwarded_port", guest: 3000, host: 3000, host_ip: "192.168.1.33"
  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.memory = "1024"
  end

  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
  SHELL

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "prometheus-setup.yml"
  end


end
