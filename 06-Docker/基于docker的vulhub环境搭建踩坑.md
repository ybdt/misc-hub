想使用vulhub搭建一下geoserver的复现环境，之前是在本地kali中搭建，这次想在vps上部署，本以为20分钟搞定，结果前后折腾了2个小时

### 坑1
依照vulhub官方介绍，将之前阿里云的vps更换为ubuntu 22.04
```
# Install the latest version docker
curl -s https://get.docker.com/ | sh

# Run docker service
systemctl start docker
```
结果https://get.docker.com/不能访问，解决办法，通过本地FQ的浏览器访问并复制，创建文件get-docker.sh，并将内容粘贴过来

### 坑2
```
bash get-docker.sh
```
执行get-docker.sh时，由于被墙导致在某一步骤卡住了，解决办法，get-docker.sh --mirror Aliyun

参考：  
https://github.com/docker/docker-install/issues/213  

### 坑3
```
wget https://github.com/vulhub/vulhub/archive/master.zip -O vulhub-master.zip
```
一开始下载失败，多试了几次，我这边成功了

### 坑4
```
# Compile environment
docker compose build

# Run environment
docker compose up -d
```
拉取镜像失败，解决办法：  
01 touch /etc/docker/daemon.json并粘贴阿里云的docker镜像源，还是拉取镜像失败  
02 修改/etc/resolv.conf中的DNS为8.8.4.4，清理DNS缓存，使用dig测试，还是拉取镜像失败  
03 将多个镜像源添加到/etc/docker/daemon.json，多等了一会，成功拉取到镜像  

参考：  
https://cr.console.aliyun.com/cn-hangzhou/instances/mirrors  
https://blog.csdn.net/qq_45997906/article/details/135472495  
https://blog.csdn.net/weixin_43822878/article/details/140016708  