Vagrant.configure("2") do |config|

    config.vm.define "apache1" do |apache1|
      apache1.vm.box = "ubuntu/bionic64"
      apache1.vm.network "private_network", ip: "192.168.33.10"
      apache1.vm.provider "virtualbox" do |vb|
        vb.memory = "512"
        vb.cpus = 1
      end
      apache1.vm.synced_folder ".", "/var/www/html"
      apache1.vm.provision "ansible" do |ansible|
        ansible.playbook = "setup_apache.yml"
      end
    end
  
    config.vm.define "apache2" do |apache2|
      apache2.vm.box = "ubuntu/bionic64"
      apache2.vm.network "private_network", ip: "192.168.33.11"
      apache2.vm.provider "virtualbox" do |vb|
        vb.memory = "512"
        vb.cpus = 1
      end
      apache2.vm.synced_folder ".", "/var/www/html" 
      apache2.vm.provision "ansible" do |ansible|
        ansible.playbook = "setup_apache.yml"
      end
    end
  
    config.vm.define "nginx" do |nginx|
      nginx.vm.box = "ubuntu/bionic64"
      nginx.vm.network "private_network", ip: "192.168.33.12"
      nginx.vm.provider "virtualbox" do |vb|
        vb.memory = "512"
        vb.cpus = 1
      end
      nginx.vm.provision "ansible" do |ansible|
        ansible.playbook = "setup_nginx.yml"
      end
    end
  end
  