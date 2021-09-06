# redis
## set password in linux
1. sudo vi /etc/redis.conf
   restart redis
2. login redis
```
   CONFIG SET requirepass "passwd"
```
   AUTH xxx （to test）
## Redis 数据类型
Redis支持五种数据类型  
    string（字符串）  
    hash（哈希）  
    list（列表）  
    set（集合）  
    zset(sorted set：有序集合)   
## Redis 数据备份与恢复
### redis备份
```
> SAVE  
``` 
该命令将在 redis 安装目录中创建dump.rdb文件。
```
> Bgsave
```
创建 redis 备份文件也可以使用命令 BGSAVE，该命令在后台执行。
### redis恢复数据
需要恢复数据，只需将备份文件 (dump.rdb) 移动到 redis 安装目录并启动服务即可。  
获取 redis 目录可以使用 CONFIG 命令  
```
> CONFIG GET dir
```
## Redis与数据库数据同步解决方案
### 数据库同步到Redis
#### 缓存
循缓存的语义规定：   
读：读缓存redis，没有，读mysql，并将mysql的值写入到redis。   
写：写mysql，成功后，更新或者失效掉缓存redis中的值。  
#### binlog
原理  
1、DBAsync伪装自己为mysql slave，向mysql master发送dump协议  
2、mysql master收到dump请求，开始推送binary log给DBAsync  
3、DBAsync解析binary log，将数据改动同步到下游(MQ、DB…)  
工作流程  
1、启动解析配置文件。  
2、注册响应处理函数。  
3、如果没有binglog相关的信息，执行mysqldump进行同步；并记录相应的binglog信息。  
4、通过COM_BINLOG_DUMP命令，将binglog的文件名、偏移量发送给MYSQL。  
5、监听Binglog的变更。  
6、获取Binlog变更后进行解析，调用回调函数。  
7、将变更编码后发送到下游。  
8、处理成功后存储binlog文件名以及偏移量。  
注：调用处理函数多线程处理
