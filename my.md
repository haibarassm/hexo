java -jar 名称.jar --spring.profiles.active=prod

JAVA_HOME=/usr/java/jdk1.8.0_191
CLASSPATH=$JAVA_HOME/lib/
PATH=$PATH:$JAVA_HOME/bin
export PATH JAVA_HOME CLASSPATH  

-- 修改策略，使得powershell能运行脚本
set-executionpolicy remotesigned

-- 查看powershell版本  
$PSVersionTable