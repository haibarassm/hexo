# linux commends
## ports
ss -tunlp  查询端口号占用情况  

## user
last 命令：显示当前与过去登录系统的用户的信息  
users 命令：显示当前当登录的用户的用户名  
who 命令：显示当前当登录的用户的信息  
修改密码 passwd xxx
## docker
docker ps 查看当前正在运行的容器  

## tar
.tar.gz 和 .tgz  
解压：tar zxvf FileName.tar.gz  
压缩：tar zcvf FileName.tar.gz DirName  
 
.zip  
解压：unzip FileName.zip  
压缩：zip FileName.zip DirName  

 ## cp 
cp -r 源目录 目标目录  
cp 源文件 目标文件  

# restart ssh in centOS7
systemctl restart sshd

## reload source
配置文件目录  
source /etc/profile  
## mongodb install tips
/etc/mongod.conf  
bindIp: 0.0.0.0  
(# Enter 0.0.0.0,:: to bind to all IPv4 and IPv6 addresses or, alternatively, use the net.bindIpAll setting.)

## mysql配置
### 第一次设置权限的操作
1. 你先装完
2. 获取默认密码
```
$ grep "A temporary password" /var/log/mysqld.log

> [Note] A temporary password is generated for root@localhost: hjkygMukj5+t783
```
3. 设置root密码
```
mysql_secure_installation
```
然后他会让你输入原来的默认密码,正确之后会让你输入新的密码,新的密码要大小写 标点(@,#之类的)再加数字
4. 初始化设置
```
Remove anonymous users? (Press y|Y for Yes, any other key for No) : y

Disallow root login remotely? (Press y|Y for Yes, any other key for No) : y

Remove test database and access to it? (Press y|Y for Yes, any other key for No) : y

Reload privilege tables now? (Press y|Y for Yes, any other key for No) : y
```
### mysql远程连接
1. 修改配置文件
```
vim /etc/mysqld.cnf
```
找到bind-address那一行,将值修改成
```
bind-address=0.0.0.0
```
然后重启
```
sudo systemctl restart mysqld
```
连接mysql
```
mysql -u root -p
```
登录之后在mysql里输入命令
```
GRANT ALL PRIVILEGES ON *.* TO 'root'@'%';
UPDATE mysql.user SET host='%' WHERE user='root';
```
然后重启mysql
```
sudo systemctl mysqld restart
```
2. 防火墙放行

## redis 
### 去除远程访问限制 
1. 修改配置文件
```
vim /etc/redis.conf
```
找到bind-address那一行,将值修改成
```
bind-address=0.0.0.0
```
2. 防火墙放行