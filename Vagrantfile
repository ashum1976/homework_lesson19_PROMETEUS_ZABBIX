# -*- mode: ruby -*-
# vi: set ft=ruby :
ENV["LC_ALL"] = "en_US.UTF-8"
Vagrant.configure(2) do |config|
          if Vagrant.has_plugin?("vagrant-timezone")
              config.timezone.value = "Europe/Minsk"
          end
            config.vm.box = "centos/7"
            config.vm.define "zablinuxsrv" do |srv|
                srv.vm.network "private_network", ip: "192.168.50.10", virtualbox__extnet: "net1"
                srv.vm.hostname = "zablinsrv"
                config.vm.provider "virtualbox" do |v|
                    v.memory = 256
                    v.cpus = 1
                end
#            prod.vm.provision "shell", path: "run_script.sh"
            end
            config.vm.define "zablinuxcl" do |cl|
                cl.vm.network "private_network", ip: "192.168.50.11", virtualbox__extnet: "net1"
                cl.vm.hostname = "zablincl"
                config.vm.provider "virtualbox" do |v|
                    v.memory = 256
                    v.cpus = 1
                end
#            prod.vm.provision "shell", path: "run_script.sh"
            end
#
end
