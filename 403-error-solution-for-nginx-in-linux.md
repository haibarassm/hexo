---
title: 403 error solution for nginx in linux
date: 2019-06-25 07:24:03
utcOffset: utf-8
tags: linux
---
## nginx 403 error solution
 1. Check the permissions on /,/root,/root/hexo/,/root/hexo/public  
 tips : To easily display all the permissions on a path, you can use namei -om /path/to/check
 2. To check if SELinux is running
 ```
 getenforce
 ```
 3. To disable SELinux until next reboot
 ```
 setenforce Permissive
 ```
 4. Restart Nginx and see if the problem persists. To allow nginx to serve your www directory (make sure you turn SELinux back on before testing this. i.e, setenforce Enforcing)
 ```
 chcon -Rt httpd_sys_content_t /root/hexo/public  
 ```