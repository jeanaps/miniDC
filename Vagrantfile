Vagrant.configure("2") do |config|

#Geral
config.vm.box = "ubuntu/bionic64"
#Máquina MiniDC-Database
  config.vm.define "database" do |database|
#    database.vm.box = "database"
    database.vm.hostname = "database"
    database.vm.network "private_network", ip: "172.17.177.21"
    database.vm.provider "virtualbox" do |v|
      v.name = "MiniDC-Database"
      v.memory = 1024
      v.cpus = 2
    end
  end

#Máquina MiniDC-Blog
  config.vm.define "blog" do |blog|
#    blog.vm.box = "blog"
    blog.vm.hostname = "blog"
    blog.vm.define "MiniDC-Blog"
    blog.vm.network "private_network", ip: "172.17.177.22"
    blog.vm.provider "virtualbox" do |v|
      v.name = "MiniDC-Blog"
      v.memory = 1024
      v.cpus = 2
    end
  end

#Máquina MiniDC
  config.vm.define "controller" do |controller|
#    controller.vm.box = "controller"
    controller.vm.hostname = "controller"
    controller.vm.define "MiniDC-AnsibleController"
    controller.vm.network "private_network", ip: "172.17.177.11"
    controller.vm.provider "virtualbox" do |v|
      v.name = "MiniDC-Ansiblecontroller"
      v.memory = 1024
      v.cpus = 2
    end
  end
end
