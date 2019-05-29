---
layout:     post
title:      Ubuntu搭建LAMP环境
subtitle:   札记
date:       2017-04-10
author:     0xl00se
header-img: img/post-bg-web.jpg
catalog: true
tags:
    - Ubuntu
    - LAMP
    - 札记
---
1.`sudo apt-get install apache2 php5-mysql libapache2-mod-php5
mysql-server`，安装完成后地址栏输入`http://localhost`回车，如果安装成功可以看到一段文字。

2.编写一个测试样本：

`sudo touch /var/www/html/test.php`

`sudo vim /var/www/html/test.php`

输入`<?php phpinfo() ?>`，然后访问`http://localhost/test.php`查看运行结果。

3.`sudo apt-get install php5`

4.`sudo apt-get install php5-gd php5-curl php5-xdebug`

5.`sudo vim
/etc/apache2/sites-enabled/0xxx`，修改`DocumentRoot`为`/var/www/html/`。

6.`sudo vim /etc/hosts,添加“127.0.0.1 mysite.com`到文件当中。

7.最后在`/etc/apache2/sites-enabled/`下面新建一个名为`www.mysite.com`的文件，最好直接复制一份`0xxx`开头的配置文件做修改就行。修改后结果如下图所示：

![](/img/2017-04-10-Ubuntu搭建LAMP环境_images/20ad8b88.png)
