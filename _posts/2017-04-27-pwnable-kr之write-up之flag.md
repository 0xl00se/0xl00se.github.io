---
layout:     post
title:      pwnable.kr之write up之flag
subtitle:   CTF
date:       2017-04-27
author:     0xl00se
header-img: img/post-bg-web.jpg
catalog: true
tags:
    - pwnable.kr
    - write up
    - flag
    - CTF
---
1.准备工作: 
```
git clone https://github.com/longld/peda.git ~/peda
echo "source ~/peda/peda.py" >> ~/.gdbinit
```
安装gdb的一个扩展工具——`Python Exploit Development Assistance for GDB`

2.执行`strings flag`查询flag的壳类型。

![](/img/2017-04-27-pwnable-kr之write-up之flag_images/222c0a0e.png)

3.发现flag文件壳类型为upx,接下来使用upx工具脱壳处理。

![](/img/2017-04-27-pwnable-kr之write-up之flag_images/e1f6c725.png)

4.执行`gdb -q ./fg`命令开始调试fg文件。

![](/img/2017-04-27-pwnable-kr之write-up之flag_images/9b0f0a4d.png)

5.继续执行`pdisass main`命令。

![](/img/2017-04-27-pwnable-kr之write-up之flag_images/ad59d909.png)

6.在`main+39`设置断点。

![](/img/2017-04-27-pwnable-kr之write-up之flag_images/2d223807.png)

7.执行`r`命令运行到断点。

![](/img/2017-04-27-pwnable-kr之write-up之flag_images/65c8541b.png)

8.上图已经发现flag了，为了优雅的显示。执行`x/s $rdx`命令即可。

![](/img/2017-04-27-pwnable-kr之write-up之flag_images/64670426.png)
