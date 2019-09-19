---
title: linux
date: 2019-09-19 10:32:03
utcOffset: utf-8
tags: linux
---
## basic option
### rename file or  directories in linux 
```
mv [OPTIONS] source destination
```
### cp 
```
cp -r
```
 源目录 目标目录 
``` 
cp 
```
源文件 目标文件 

## reload source
配置文件目录  
```
source /etc/profile  
```
## ports
```
ss -tunlp 
```
查询端口号占用情况   
## user
```
sudo -i
```
change user to root
```
last
```
显示当前与过去登录系统的用户的信息  
```
users
```
显示当前当登录的用户的用户名  
```
who
```
显示当前当登录的用户的信息  
```
passwd
```
修改密码  
## docker
```
docker ps
```
查看当前正在运行的容器  

## zip and unzip
### .tar.gz 和 .tgz  
解压
```
tar zxvf FileName.tar.gz  
```
压缩
```
tar zcvf FileName.tar.gz DirName  
```

### .zip  
解压
```
unzip FileName.zip  
```
压缩
```
zip FileName.zip DirName  
```
##
### mongodb install tips
```
sudo vi /etc/mongod.conf  
```
change bindIp from 127.0.0.1 to 0.0.0.0  
(# Enter 0.0.0.0,:: to bind to all IPv4 and IPv6 addresses or, alternatively, use the net.bindIpAll setting.)
### mongodb remove steps
1. Stop MongoDB
```
sudo systemctl stop mongod 
```
2. Remove Packages
```
sudo yum erase $(rpm -qa | grep mongodb-org)
```
3. Remove Data Directories.
```
sudo rm -r /var/log/mongodb
sudo rm -r /var/lib/mongo
```
if don't excute step 3 ,you will receive error like unchecked users or so on when you reinstall mongodb
## nginx
### nginx start&restart  
```
sudo systemctl start nginx  
```
after something change remember to reload nginx
### check the nginx status
```
sudo systemctl status nginx  
```
## firewall
### firewall config
```
sudo firewall-cmd --permanent --zone=public --add-service=http 
sudo firewall-cmd --permanent --zone=public --add-service=https
sudo firewall-cmd --permanent --zone=public --add-port=1024-65535/tcp  
sudo firewall-cmd --reload
sudo firewall-cmd --state  
```
## consul
### run agent with 
```
consul agent -dev  -client 0.0.0.0 -ui
```
## rpm unzip code
```
rpm -i filename.rpm
```