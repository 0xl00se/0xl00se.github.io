---
layout:     post
title:      Linux下db2的TCP服务配置
subtitle:   札记
date:       2017-10-17
author:     0xl00se
header-img: img/post-bg-web.jpg
catalog: true
tags:
    - Linux
    - db2
    - TCP
    - 札记
---
1.安装完DB2后。需要对DB2进行设置，以便开启DB2的TCP服务。

2.切换到db2的用户下，执行`su – db2inst1`命令。

3.查看db2是否开启tcp服务，执行`db2set -all`命令，如果没有看到如下内容`DB2COMM=TCPIP`,执行`db2set
db2COMM=TCPIP`命令。

4.查看是否配置db2的TCP服务名称db2，执行`get dbm cfg | grep -i SVCENAME`命令。
若显示如下所示： 
```
TCP/IP Service name (SVCENAME) = 
SSL service name (SSL_SVCENAME) = 
```
则需要设置DB2的TCP服务名称，执行`db2 update database
manager configuration using svcename db2AppName（自定义名称）`命令
 
 5.执行`cat /etc/services | grep
 db2`命令，查看是否已经将db2的tcp服务添加到系统服务中。 若没有，则vim
 /etc/services命令添加`db2AppName 50000/tcp`到文件末尾。

6.重启db2服务。执行`db2 force application all;db2stop;db2start`命令。

7.查看db2 tcp服务监听的端口是否已经启用，执行`netstat -na | grep 50000`命令。
若出现如下图示，说明db2 tcp 服务配置成功。 
```
tcp 0 0 0.0.0.0:50000 0.0.0.0:*  LISTEN
```
