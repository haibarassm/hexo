一个就add-port=后面一个
firewall-cmd --permanent --zone=public --add-port=1024-65535/tcp  
firewall-cmd --state  
firewall-cmd --reload  