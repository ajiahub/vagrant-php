# lnmp
Vagrant box for PHP projects
因github支持上传的文件最大为2G，本box源放在百度网盘，see:https://pan.baidu.com/s/1hGTT2yLSs65mYqEuOB7Tqg

# Include
*  centos/6.7
*  nginx/1.12.2
*  mariadb/10.1.23
*  php/7.1.7
*  python2.6.7
*  composer

# Install
项目地址: (`git clone`)
```
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

# Configuration
有host-only access/private_network/public_network三种模式可供选择
因本地单机开发，本配置选择为private_network
本地集群参考：https://www.vagrantup.com/docs/multi-machine/
```
Vagrant.configure("2") do |config|
config.vm.box = "lnmp"
config.vm.network "private_network", ip: "192.168.33.10"
	config.vm.provider "virtualbox" do |vb|
		vb.gui = false
		vb.memory = "2048"
	end
end
```

# 效果截图：
![image](https://ragonli.com/statics/images/version.png)
![image](https://ragonli.com/statics/images/phpinfo.png)
![image](https://ragonli.com/statics/images/p.png)

# Tips：
vagrant虚拟硬盘在10G以上，内存在2G内上
推荐vagrant版本1.8.6，virtualBox 5.1.8

# 扫码加微信交流：
![image](https://ragonli.com/statics/images/ligang.png)

# 赞助：
if it's helpful for you,just Sponsor a cup of coffee  
![image](https://ragonli.com/statics/images/ali_pay.png)
![image](https://ragonli.com/statics/images/wechat_pay.png)

