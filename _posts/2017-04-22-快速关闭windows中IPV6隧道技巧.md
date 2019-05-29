---
layout:     post
title:      快速关闭windows中IPV6隧道技巧
subtitle:   札记
date:       2017-04-22
author:     0xl00se
header-img: img/post-bg-web.jpg
catalog: true
tags:
    - windows
    - IPV6隧道
    - 札记
---
1.禁用IPv6命令

`netsh interface teredo set state disable`

`netsh interface 6to4 set state disabled`

`netsh interface isatap set state disabled`

2.启用IPv6命令

`netsh interface teredo set state default`

`netsh interface 6to4 set state default`

`netsh interface isatap set state default`
