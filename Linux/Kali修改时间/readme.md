# 修改时区
执行如下命令，按照提示选择Asia->China->Beijing Time
```
tzselect
```
将如下命令添加到家目录下的.profile文件末尾，重新登录即可
```
TZ='Asia/Shanghai'; export TZ
```

参考链接：  
https://blog.csdn.net/neuisf/article/details/104179978


# 修改日期时间
执行如下命令修改系统日期时间
```
ddate -s "2023-08-23 08:33:24"
```
结果发现日期时间没生效

执行如下命令查看系统时间
```
timedatectl
```
执行如下命令关闭ntp同步
```
timedatectl set-ntp false
```
再次执行修改系统日期时间命令

参考链接：  
https://blog.csdn.net/weixin_43894312/article/details/103710667