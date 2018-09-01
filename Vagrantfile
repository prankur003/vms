Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/trusty64"
    config.vm.network "private_network", ip: "192.168.33.10"
    config.vm.provider "virtualbox" do |vb|
      vb.gui = false
      vb.customize ["modifyvm", :id, "--memory", "2048", "--cpus", "2"]
    end

    config.vm.provision "shell", inline: <<-SHELL
     
      add-apt-repository ppa:openjdk-r/ppa -y
      apt-get update
      echo "\n----- Installing Apache and Java 8 ------\n"
      apt-get -y install openjdk-8-jdk
      update-alternatives --config java
      apt-get install -y git
      curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
      apt-get install -y nodejs
      apt-get update
      apt-get upgrade -y
      apt-get autoremove -y
   SHELL
end
