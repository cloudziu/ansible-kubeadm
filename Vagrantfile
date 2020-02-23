
Vagrant.configure("2") do |config|
  config.ssh.insert_key = false

  config.vm.provider "virtualbox" do |v|
      v.memory = 3072
      v.cpus = 2
  end
    
  config.vm.define "node-master" do |master|
      master.vm.box = "ubuntu/xenial64"
      master.vm.network "private_network", ip: "10.1.0.10"
      master.vm.hostname = "ubuntu-master"
      config.vm.provision "file", source: "~/.ssh/id_rsa.pub", destination: "~/.ssh/me.pub"
      config.vm.provision "shell", inline: <<-SHELL
      cat /home/vagrant/.ssh/me.pub >> /home/vagrant/.ssh/authorized_keys
      SHELL
            
  end

  
  config.vm.define "node-1" do |node|
      node.vm.box = "ubuntu/xenial64"
      node.vm.network "private_network", ip: "10.1.0.11"
      node.vm.hostname = "node-1"
      config.vm.provision "file", source: "~/.ssh/id_rsa.pub", destination: "~/.ssh/me.pub"
      config.vm.provision "shell", inline: <<-SHELL
      cat /home/vagrant/.ssh/me.pub >> /home/vagrant/.ssh/authorized_keys
      SHELL
      
  end


  config.vm.define "node-2" do |node|
      node.vm.box = "ubuntu/xenial64"
      node.vm.network "private_network", ip: "10.1.0.12"
      node.vm.hostname = "node-2"
      config.vm.provision "file", source: "~/.ssh/id_rsa.pub", destination: "~/.ssh/me.pub"
      config.vm.provision "shell", inline: <<-SHELL
      cat /home/vagrant/.ssh/me.pub >> /home/vagrant/.ssh/authorized_keys
      SHELL
      
  end
    
end

