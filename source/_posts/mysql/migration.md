---
title: migrate mysql data
categories:
  - mysql
tags:
  - mysql
---

# Migrate MySQL Data
## Background
Mysql is installed in root directory, and the data is stored in `/var/lib/mysql` directory.
When the root directory is not sufficient for the data.
we need to migrate the data to another directory.
```bash
mysql --version 
mysql  Ver 8.0.41-0ubuntu0.20.04.1 for Linux on x86_64 ((Ubuntu))
```

## Modify the mysql configuration file
First stop the mysql service.
```bash
sudo systemctl stop mysql
```

Then create a new directory for the mysql data.
The config file is located in `/etc/mysql/mysql.conf.d/mysqld.cnf` file.

```bash
vim /etc/mysql/mysql.conf.d/mysqld.cnf
```
Then add or overwrite the following lines to the file.
```bash
datadir=/home/mysql/mysql
socket=/home/mysql/mysql/mysql.sock

log-error=/home/mysql/log/mysqld.log
pid-file=/home/mysql/run/mysqld/mysqld.pid
```
## Create the new directory
```bash
sudo mkdir -p /home/mysql/mysql
sudo mkdir -p /home/mysql/log
touch /home/mysql/log/mysqld.log
sudo mkdir -p /home/mysql/run/mysqld
```

## Change the ownership
```bash
cp -ar /var/lib/mysql/ /home/mysql/mysql/
sudo chown -R mysql:mysql /home/mysql
sudo chmod 777 /home/mysql
```

## Change the AppArmor configuration
```bash
sudo vim /etc/apparmor.d/usr.sbin.mysqld
# add this line at the end of the file
alias /var/lib/mysql/ -> /home/mysql/,
# then restart
systemctl restart apparmor
```

## Start the mysql service
```bash
sudo systemctl start mysql
# delete the old files
rm -rf /var/lib/mysql
```



