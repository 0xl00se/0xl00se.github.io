---
layout:     post
title:      ubuntu之grub rescue修复指南
subtitle:   札记
date:       2017-11-17
author:     0xl00se
header-img: img/post-bg-web.jpg
catalog: true
tags:
    - ubuntu
    - grub rescue
    - 参考指南
    - 札记
---
1.`grub rescue>ls` 列出硬盘上所有的分区。

2.`grub rescue>ls （hd0，sda*)/boot` 寻找安装ubuntu的磁盘分区。

3.`grub rescue>set root=(hd0, sda*)`

4.`grub rescue>set prefix=(hd0, sda*)/boot/grub`

5.`grub rescue>insmod /boot/grub/normal.mod`

6.`grub rescue>normal`
,即可进入boot/grub的启动界面了。如果grub也损坏了，执行下一步。

7.进入grub命令行 
```
grub> root (hd0,8) # 指定包含vmlinuz-2.6.18-274.7.1.el5和initrd-2.6.18-274.7.1.el5.img的partition
grub> kernel /boot/vmlinuz-2.6.18-274.7.1.el5 ro root=/dev/sda8 # root= 是指定包含/sbin/init的partition，即挂载/的partition（以Linux的角度）
grub> initrd /boot/initrd-2.6.18-274.7.1.el5.img # 据说这项可以省略
grub> boot
```
8.进入ubuntu操作系统后，打开终端，执行如下命令： 
```
sudo update-grub2
sudo grub-install/dev/sda
```
9.修复完成。
