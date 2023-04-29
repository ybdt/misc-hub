---
title: 通达OA漏洞研究
date: 2022-04-28 17:27:27
tags: 代码审计
---

# 前言
如下是我研究通达OA时的经验、技巧
<!--more-->
# 0x01-历史版本下载
```
http://cdndown.tongda2000.com/oa/2019/TDOA11.10.exe
经验证可下载TDOA11.2.exe到TDOA11.10.exe

研究通达OA漏洞期间，记得看到过2017版的安装包名好像是MYOA2017.exe，经测试如下链接可下载
https://cdndown.tongda2000.com/oa/2017/MYOA2017.exe

其他版本同理：2015、2010、2009

还差版本2013、2011
```

# 0x02-版本查看
```
适用于2017、2016、2015、2013、2010、2009、2008
http://192.168.0.116/inc/expired.php

适用于11.x系列
暂不放出
```

# 0x03-默认口令
```
用户名：admin
密码：（密码为空）
```

# 0x04-空间测绘
```
fofa搜索关键字：title="通达OA"
fofa搜索关键字：app="TDXK-通达OA"
hunter搜索关键字：app.vendor="通达"

参考链接：
https://www.bilibili.com/read/cv10888579
```

# 0x05-动态调试技巧
```
用解密后的php文件替换原加密php文件，可用于动态调试
```

# 0x06-适配最新版11.10的后台rce 0day
```
暂不放出
```