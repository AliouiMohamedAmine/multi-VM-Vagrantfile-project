Vagrant.configure("2") do |config|
    # Define the box for all VMs
  
    # Define the first web VM - web01
    config.vm.define "web01" do |web01|
      web01.vm.box = "ubuntu/focal64"  # Default for Ubuntu 20.04, you can change this to a more specific one  
      web01.vm.hostname = "web01"
      web01.vm.network "private_network", ip: "192.168.99.41"
    end
  
    # Define the second web VM - web02
    config.vm.define "web02" do |web02|
      web02.vm.box = "ubuntu/focal64"   
      web02.vm.hostname = "web02"
      web02.vm.network "private_network", ip: "192.168.99.42"
    end

    config.vm.define "web03" do |web03|
        web03.vm.box = "ubuntu/focal64"  # Default for Ubuntu 20.04, you can change this to a more specific one  
        web03.vm.hostname = "web03"
        web03.vm.network "private_network", ip: "192.168.99.44"
    end
  
    # Define the database VM - db01
    config.vm.define "db01" do |db01|
      db01.vm.hostname = "db01"
      db01.vm.network "private_network",  ip: "192.168.99.43"
      db01.vm.provision "shell", inline: <<-SHELL
        yum install -y wget unzip mariadb-server -y
        systemctl start mariadb
        systemctl enable mariadb
        SHELL
      db01.vm.box = "centos/7"  # CentOS 7 Box
    end
  
  end
  