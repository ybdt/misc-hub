# 0x01-项目起源
梳理一下红队Web打点中的信息收集、指纹识别，目标是成体系化，尽量防止遗漏

# 0x02-免责声明
该项目仅供授权下使用，禁止使用该项目进行违法操作，否则自行承担后果，请各位遵守《中华人民共和国网络安全法》！！！

```
先收集离目标最近的资产，目的是快速打下比较正的点，实在没点可打，再逐渐扩大范围
```

# 0x03-收集资产--手动

## 01-旁站收集
```
先通过本地ping及多地ping判断目标是否使用CDN

未使用CDN时
先通过空间测绘快速获取目标开放的全部端口，同时通过nmap扫描目标全端口，查看是否开放其他端口

使用CDN时
下一项
```
## 02-子域收集
```
通过FOFA收集子域：https://fofa.info/
通过OneForAll收集子域：https://github.com/shmilylty/OneForAll
通过esd收集子域：https://github.com/FeeiCN/ESD
```
## 03-C段收集
```
由旁站收集步骤获知目标是否使用CDN

未使用CDN时
通过收集到的子域，推测目标IP段为半个B段、C段、半个C段...

使用CDN时
通过收集到的子域，推测目标的大概C段
```
## 04-根域收集
```
通过“ICP/IP地址/域名信息备案管理系统”（https://beian.miit.gov.cn/#/Integrated/index）收集目标根域
```
## 05-父子公司收集
```
父子公司不是很多时，可通过天眼查、企查查手动收集

父子公司很多时，可通过ENScan自动化收集（ENScan借助百度的爱企查）
```
## 06-ASN收集
```
当目标组织很大时，可考虑收集目标所在ASN的全部资产
```
## 07-历史IP收集
```
通过ip138.com查看目标域名解析过的历史IP
```
## 08-Google Dork收集
```
收集目标相关的关键字，通过google dork收集目标关联资产

语法
allintitle:毕节 电网 系统
program site:google.com

参考链接
https://blog.csdn.net/u014565127/article/details/53842885
https://blog.csdn.net/u014565127/article/details/53868443
```

# 0x04-收集资产--自动化

## 01-水泽
地址：https://github.com/0x727/ShuiZe_0x727

## 02-灯塔
地址：https://github.com/TophantTechnology/ARL

## 03-Kunyu
地址：https://github.com/knownsec/Kunyu

# 0x05-资产收集--优秀项目
```
https://github.com/r0eXpeR/GetInfo
https://github.com/projectdiscovery/uncover -- 包含fofa、shodan、censys
https://github.com/ExpLangcn/WanLi -- 包含fofa、quake
```

# 0x06-指纹识别-手动
```
http://whatweb.bugscaner.com/look/
https://www.yunsee.cn/
http://finger.tidesec.com/
https://scan.top15.cn/web/
https://fp.shuziguanxing.com/#/
```

# 0x07-指纹识别--自动化
```
https://github.com/EASY233/Finger
```

# 0x08-指纹识别--优秀项目
```
https://github.com/ShiHuang-ESec/EHole
https://github.com/EdgeSecurityTeam/EHole
https://github.com/winezer0/whatweb-plus
https://github.com/r0eXpeR/fingerprint
```