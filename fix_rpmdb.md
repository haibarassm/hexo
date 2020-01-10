---
title: Thread died in Berkeley DB library
date: 2020-01-10 13:01:03
utcOffset: utf-8
tags: linux
---
# Fix rpmdb: Thread died in Berkeley DB library
## error
Thread died in Berkeley DB library
## possiable reason
your rmp database was broken 
## solution
rebuild the rpmdb database
```
mkdir /var/lib/rpm/backup
cp -a /var/lib/rpm/__db* /var/lib/rpm/backup/
rm -f /var/lib/rpm/__db.[0-9][0-9]*
rpm --quiet -qa
rpm --rebuilddb
yum clean all
```