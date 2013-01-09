# -*- mode: ruby -*-
# vi: set ft=ruby :

# vagrant box add https://github.com/downloads/roderik/VagrantQuantal64Box/quantal64.box
Vagrant::Config.run do |config|
  config.vm.box = "nginx_php"
  config.vm.network :hostonly, "192.168.33.10"
  config.vm.forward_port 80, 8080
  config.vm.customize do |vm|
    vm.memory_size = 256
  end

  config.vm.share_folder "example.com", "/var/www/example.com", "/var/www/example.com"
  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = ["cookbooks"]
    chef.add_recipe "nginx"
    chef.add_recipe "apt"
    chef.add_recipe "build-essential"
    chef.add_recipe "php-fpm"
    chef.add_recipe "nginx"
    chef.add_recipe "php"
    chef.add_recipe "php::mysql"
    chef.add_recipe "mysql"
    chef.add_recipe "mysql::server"
    chef.add_recipe "git"
    chef.json = {
        :mysql => {
            :server_root_password => "yourpass",
            :server_repl_password => "yourpass",
            :server_debian_password => "yourpass"
        } 
    }
  end
end
