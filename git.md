---
title: git
date: 2019-06-26 17:04:03
utcOffset: utf-8
tags: git
---
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
## cancle commits but is not push
```
git reset --soft HEAD^
```
HEAD^的意思是上一个版本，也可以写成HEAD~1
撤回多次就~N