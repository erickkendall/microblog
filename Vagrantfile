Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.network "private_network", ip: "192.168.33.10"
  
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
  end

  # Run update and install commands during provisioning
  config.vm.provision "shell", inline: <<-SHELL
    # Update package list and install required packages
    sudo apt-get -y update
    sudo apt-get -y install python3 python3-venv mysql-server postfix supervisor nginx git
  SHELL
end
