Vagrant.configure("2") do |config|
  # Указываем имя базового образа
  config.vm.box = "centos/8"

  # Настраиваем каждую ВМ
  config.vm.define "lb.fe" do |lbfe|
    lbfe.vm.hostname = "lb.fe"
    lbfe.vm.network "private_network", ip: "192.168.56.10"
  end

  config.vm.define "fe1" do |fe1|
    fe1.vm.hostname = "fe1"
    fe1.vm.network "private_network", ip: "192.168.56.11"
  end

  config.vm.define "fe2" do |fe2|
    fe2.vm.hostname = "fe2"
    fe2.vm.network "private_network", ip: "192.168.56.12"
  end

  config.vm.define "lb.db" do |lbdb|
    lbdb.vm.hostname = "lb.db"
    lbdb.vm.network "private_network", ip: "192.168.56.13"
  end

  config.vm.define "master1" do |master1|
    master1.vm.hostname = "master1"
    master1.vm.network "private_network", ip: "192.168.56.14"
  end

  config.vm.define "master2" do |master2|
    master2.vm.hostname = "master2"
    master2.vm.network "private_network", ip: "192.168.56.15"
  end

  config.vm.define "slave1" do |slave1|
    slave1.vm.hostname = "slave1"
    slave1.vm.network "private_network", ip: "192.168.56.16"
  end

  config.vm.define "slave2" do |slave2|
    slave2.vm.hostname = "slave2"
    slave2.vm.network "private_network", ip: "192.168.56.17"
  end

  config.vm.define "monitoring" do |monitoring|
    monitoring.vm.hostname = "monitoring"
    monitoring.vm.network "private_network", ip: "192.168.56.18"
  end

  config.vm.define "backup" do |backup|
    backup.vm.hostname = "backup"
    backup.vm.network "private_network", ip: "192.168.56.19"
  end



  # Добавляем публичный ключ для root
  config.vm.provision "shell", inline: <<-SHELL
    mkdir -p /root/.ssh
    echo ""your id-rsa.pub >> /root/.ssh/authorized_keys
    chmod 700 /root/.ssh
    chmod 600 /root/.ssh/authorized_keys
  SHELL
end

