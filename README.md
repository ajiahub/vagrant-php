# lnmp
Vagrant box for PHP projects,因github最大支持2G，box源放在百度网盘，see:

#Include
*  centos/6.7
*  nginx/1.12.2
*  mariadb/10.1.23
*  php/7.1.7
*  python2.6.7
*  composer

#Install
项目地址: (`git clone`)
```shell
git clone https://github.com/chinahub/lnmp.git
```
建立box镜像关联
```
vagrant box add lnmpBox lnmp.box
```
初始化
```
vagrant init lnmpBox
```
启动虚拟机
```
vagrant up
```

#Configuration
有host-only access/private_network/public_network三种模式可供选择
```
# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
# The most common configuration options are documented and commented below.
# For a complete reference, please see the online documentation at
# https://docs.vagrantup.com.

# Every Vagrant development environment requires a box. You can search for
# boxes at https://atlas.hashicorp.com/search.
config.vm.box = "lnmp"

# Disable automatic box update checking. If you disable this, then
# boxes will only be checked for updates when the user runs
# `vagrant box outdated`. This is not recommended.
# config.vm.box_check_update = false

# Create a forwarded port mapping which allows access to a specific port
# within the machine from a port on the host machine. In the example below,
# accessing "localhost:8080" will access port 80 on the guest machine.
# config.vm.network "forwarded_port", guest: 80, host: 8080

# Create a private network, which allows host-only access to the machine
# using a specific IP.
config.vm.network "private_network", ip: "192.168.33.10"

# Create a public network, which generally matched to bridged network.
# Bridged networks make the machine appear as another physical device on
# your network.
# config.vm.network "public_network"

# Share an additional folder to the guest VM. The first argument is
# the path on the host to the actual folder. The second argument is
# the path on the guest to mount the folder. And the optional third
# argument is a set of non-required options.
# config.vm.synced_folder "../data", "/vagrant_data"

# Provider-specific configuration so you can fine-tune various
# backing providers for Vagrant. These expose provider-specific options.
# Example for VirtualBox:
#
config.vm.provider "virtualbox" do |vb|
#   # Display the VirtualBox GUI when booting the machine
vb.gui = false
#
#   # Customize the amount of memory on the VM:
vb.memory = "2048"
end
#
# View the documentation for the provider you are using for more
# information on available options.

# Define a Vagrant Push strategy for pushing to Atlas. Other push strategies
# such as FTP and Heroku are also available. See the documentation at
# https://docs.vagrantup.com/v2/push/atlas.html for more information.
# config.push.define "atlas" do |push|
#   push.app = "YOUR_ATLAS_USERNAME/YOUR_APPLICATION_NAME"
# end

# Enable provisioning with a shell script. Additional provisioners such as
# Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
# documentation for more information about their specific syntax and use.
# config.vm.provision "shell", inline: <<-SHELL
#   apt-get update
#   apt-get install -y apache2
# SHELL
end
```

#效果截图：
![image](https://ragonli.com/statics/images/version.png)
![image](https://ragonli.com/statics/images/phpinfo.png)
![image](https://ragonli.com/statics/images/p.png)

#Tips：
vagrant虚拟硬盘在10G以上，内存在2G内上。
推荐vagrant版本1.8.6，virtualBox 5.1.8

#扫码加微信交流：
![image](https://ragonli.com/statics/images/ligang.png)

