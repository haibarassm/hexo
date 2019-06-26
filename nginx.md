# nginx
## nginx start/restart
```
sudo systemctl start nginx  
``` 
after something change remember to reload nginx
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
## set username and password of git groblelly in linux 
1. When running this command, the first time you pull or push from the remote repository, you'll get asked about the username and password.  
Afterwards, for consequent communications with the remote repository you don't have to provide the username and password
```
git config --global credential.helper store
```
2. set by yourselef
```
git config --global user.name "your username"
git config --global user.password "your password"
```
## rename file or  directories in linux 
```
mv [OPTIONS] source destination
```