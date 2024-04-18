# 前言
之前都是用2套渗透环境，Win10 + Kali，占用资源不说，时间一久，工具繁多，不利于整理，一直想改成一套环境，在搞的过程中碰到很多坑，本文属于简单记录，希望可以帮助到其他人  

# 0x01-整体思路
在Win10下安装WSL，以及在WSL下安装docker，这样Linux下的工具基本都能在Windows下用

# 0x02-过程记录
Win10下的WSL安装较简单，注册一个Windows Store账户，即可安装WSL，我这里安装的是Ubuntu18.04  
不过有些系统在登录账户时会碰到“执行此操作需要Internet”的问题，查阅过说是微软的问题，网上的办法都试过，均无效，暂时没有办法

接下来是一波三折的安装Docker  
在Windows的WSL下安装docker后，docker没有启动，systemctl不能使用，sudo service docker start也不能启动docker

改为通过Docker Desktop安装docker，安装后仍旧不能启动

按照网上文章取消勾选docker engine后，docker desktop提示需要docker engine

查阅其他文章：WSL 2 上的 Docker 远程容器入门  
参考：https://docs.microsoft.com/zh-cn/windows/wsl/tutorials/wsl-containers

WSL1升级为WSL2  
参考：https://zhuanlan.zhihu.com/p/356397851

管理员powershell下启用虚拟机功能：dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart  
重启后报错，提示不支持虚拟化  
在虚拟机设置中开启虚拟化功能  
参考：https://blog.csdn.net/qq_36396763/article/details/107465600

安装时报错：a later version of the Windows ...  
下载并安装一个程序，卸载Windows Subsystem for Linux Update  
参考：https://blog.csdn.net/baidu_33340703/article/details/107129169

成功安装docker desktop  
通过在docker desktop中设置integration，可在WSL中使用docker

# 0x03-工具测试
在Windows下的docker中安装AWVS

使用镜像：docker pull xiaomimi8/awvs14-log4j-2022

拉取AWVS镜像，需要配置镜像加速，否则会卡死  
参考：https://github.com/ybdt/front-hub/tree/main/18-Docker%E7%9B%B8%E5%85%B3/2021_01_04_Docker%20Pull%E9%95%9C%E5%83%8F%E5%A6%82%E4%BD%95%E5%8A%A0%E9%80%9F

# 0x04-不足之处
当前在Windows下使用docker不足之处是，占用内存资源很多