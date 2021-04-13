# -*- mode: ruby -*-
# vi: set ft=ruby :
ENV["LC_ALL"] = "en_US.UTF-8"
Vagrant.configure(2) do |config|
          if Vagrant.has_plugin?("vagrant-timezone")
              config.timezone.value = "Europe/Minsk"
          end
          config.vm.box = "centos/8"

          config.vm.provider "virtualbox" do |v|
                    v.memory = 2048
                    v.cpus = 1
                end

            config.vm.define "zablinuxsrv" do |srv|
                #srv.vm.network "private_network", ip: "192.168.50.10", virtualbox__extnet: "net1"
                srv.vm.network "public_network", bridge: 'wlp0s19f2u2', ip: "192.168.1.16"
                srv.vm.hostname = "zablinsrv"
#               prod.vm.provision "shell", path: "run_script.sh"
                # default router
                  # srv.vm.provision "shell", run: "always",inline: "route add default gw 192.168.1.1"
                  # # delete default gw on eth0
                  # srv.vm.provision "shell",
                  # run: "always",
                  # inline: "eval `route -n | awk '{ if ( ==\"eth0\" &&  != \"0.0.0.0\") print \"route del default gw \" ; }'`"

            end

            config.vm.define "zablinuxcl" do |cl|
                #cl.vm.network "private_network", ip: "192.168.50.11", virtualbox__extnet: "net1"
                cl.vm.network "public_network", ip: "192.168.1.17"
                cl.vm.hostname = "zablincl"
                #prod.vm.provision "shell", path: "run_script.sh"
            end
end
