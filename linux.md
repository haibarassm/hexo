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

## reload source
配置文件目录  
source /etc/profile  
## mongodb install tips
/etc/mongod.conf  
bindIp: 0.0.0.0  
(# Enter 0.0.0.0,:: to bind to all IPv4 and IPv6 addresses or, alternatively, use the net.bindIpAll setting.)
