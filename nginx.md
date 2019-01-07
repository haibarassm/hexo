# nginx
## nginx start/restart
```
sudo systemctl start nginx  
```
## firewall config
```
sudo firewall-cmd --permanent --zone=public --add-service=http 
sudo firewall-cmd --permanent --zone=public --add-service=https
sudo firewall-cmd --reload
```
## check the nginx status
```
sudo systemctl status nginx  
```
