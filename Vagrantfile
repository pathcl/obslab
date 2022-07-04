Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.synced_folder '.', '/vagrant', disabled: true
  config.vm.network "forwarded_port", guest: 9090, host: 9090, host_ip: "192.168.1.34"
  config.vm.network "forwarded_port", guest: 3000, host: 3000, host_ip: "192.168.1.34"
  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.memory = "4096"
  end

  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
  SHELL

  # This is the entrypoint for ansible to install everything
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "setup.yml"
  end


end
