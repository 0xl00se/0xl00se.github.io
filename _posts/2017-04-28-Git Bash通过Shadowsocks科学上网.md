---
layout:     post
title:      Git Bash通过Shadowsocks科学上网
subtitle:   札记
date:       2017-04-28
author:     0xl00se
header-img: img/post-bg-web.jpg
catalog: true
tags:
    - Git Bash
    - Shadowsocks
    - 科学上网
    - 札记
---
1.简单粗暴，直接在bash终端输入以下命令即可，不过只对当前终端有效。 
```
export {http,https,ftp}_proxy='http://127.0.0.1:1080';
```
2.长久有效的话，需要到`/etc/bash.bashrc`文件末尾处加上上面的命令。

3.git设置和取消代理命令如下： 
``` 
git config –global http.proxy http://127.0.0.1:1080

git config –global https.proxy https://127.0.0.1:1080

git config –global –unset http.proxy

git config –global –unset https.proxy
```
