Vagrant.configure("2") do |config|
    config.vm.provider "virtualbox" do |vb|
      vb.name = "vagrant-ansible-nginx"
      vb.memory = 1024
      vb.cpus = 1
  end
    config.vm.box = "hashicorp/bionic64"    
    config.vm.network "public_network", ip: "192.168.100.211", bridge: "eno1"
    config.vm.provision "shell", path: "script.sh"  
    config.vm.synced_folder "./ansible", "/ansible"  

    config.vm.provision "ansible" do |ansible|
      ansible.playbook = "ansible/playbook_nginx.yml"
    end  
  end
  