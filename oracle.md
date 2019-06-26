# 配置步骤
1、 下载plsql和instantclient  
2、解压instantclient，在instantclient下新建  NETWORK\ADMIN\tnsnames.ora文件，在文件中进行相关配置
```
ORCL_TEST =

　　　　(DESCRIPTION =
　　　　　　(ADDRESS_LIST =
　　　　　　　　(ADDRESS = (PROTOCOL = TCP)(HOST = 127.0.0.1)(PORT = 1521))
　　　　)
　　　　(CONNECT_DATA =
　　　　　　(SERVER = DEDICATED)
　　　　　　(SERVICE_NAME = test)
　　　　)
　　)
```
3、打开plsql,配置Oracle主目录和OCI库  
4、配置环境变量
NLS_LANG （AMERICAN_AMERICA.AL32UTF8）  
ORACLE_HOME（instantclient路径）