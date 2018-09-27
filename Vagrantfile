# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.define :web1 do |web_1|
    web_1.vm.box = "ubuntu/trusty64"
    web_1.vm.provider :virtualbox do |vb_1|
vb_1.customize [ 'modifyvm', :id, '--name', 'web_1' ]
    web_1.vm.provision "shell", path: "script.sh"
    web_1.vm.network "forwarded_port", guest: 80, host: 8080
    web_1.vm.synced_folder "www_1", "/var/www/html/"
    
  config.vm.define :web2 do |web_2|
    web_2.vm.box = "ubuntu/trusty64"
    web_2.vm.provider :virtualbox do |vb_2|
 	vb_2.customize [ 'modifyvm', :id, '--name', 'web_2' ]
    web_2.vm.provision "shell", path: "script.sh"
    web_2.vm.network "forwarded_port", guest: 80, host: 8008
    web_2.vm.synced_folder "www_2", "/var/www/html/"
  end
end
