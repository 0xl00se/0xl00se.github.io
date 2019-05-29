---
layout:     post
title:      kali linux终端字符显示重叠解决方案
subtitle:   札记
date:       2017-04-10
author:     0xl00se
header-img: img/post-bg-web.jpg
catalog: true
tags:
    - kali linux
    - 札记
---
1.打开终端，输入`apt-get install tty-wqy-microhei tty-wqy-zenhei
xfonts-wqy`命令安装新字体。

2.更改字体，打开`gnome-tweak-tool`工具。将窗口标题更改为`文泉驿微米黑
Regular`,界面、文档、等宽更改为`文泉驿微米黑等宽 Regular`。

3.更新系统，输入`apt-get update && apt-get dist-upgrade`

4.reboot。
