Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.provider "virtualbox" do |vb|
   config.vm.network "public_network", ip: "10.0.0.134"
  vb.name = "desafio_03_docker"
      end
 

   config.vm.provision "shell", inline: <<-SHELL
   sudo apt -y remove docker docker-engine docker.io containerd runc
   sudo apt update
   sudo apt -y install ca-certificates curl gnupg lsb-release
   sudo mkdir -p /etc/apt/keyrings
   curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
   echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \ $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
   sudo apt-get update 
   sudo apt -y install docker-ce docker-ce-cli containerd.io docker-compose-plugin
   sudo groupadd docker 
   sudo usermod -aG docker vagrant
   newgrp docker
   apt-get install -y vim curl telnet unzip wget net-tools htop nmap
   SHELL
end


