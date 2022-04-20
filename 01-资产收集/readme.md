先收集离目标最近的资产，目的是尽可能快的打下比较正的点，实在没点可打，再逐渐扩大范围



# 0x01-手动收集资产

## 01-旁站收集
```
先通过本地ping及多地ping判断目标是否使用CDN

未使用CDN时
先通过空间测绘快速获取目标开放的全部端口，同时通过nmap扫描目标全端口，查看是否开放其他端口
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
通过收集到的子域，推测目标IP段为C段、半个C段、半个B段...

使用CDN时
通过收集到的子域，推测目标的大概C段
```
## 04-根域收集
```
通过“ICP/IP地址/域名信息备案管理系统”（https://beian.miit.gov.cn/#/Integrated/index）收集目标根域
```
## 05-父子公司收集
```
通过ENScan自动化收集目标父子公司（通过天眼查、企查查收集目标父子公司）
```
## 06-ASN收集
```
当目标组织较大时，可考虑收集目标所在ASN的全部资产
```
## 07-历史IP收集
```
通过ip138.com查看目标域名解析过的历史IP
```
## 08-Google Dork收集
```
收集目标相关的关键字，通过google dork收集目标关联资产

google dork:
https://blog.csdn.net/u014565127/article/details/53842885
https://blog.csdn.net/u014565127/article/details/53868443
allintitle:毕节 电网 系统
program site:google.com
```



# 0x01-自动化收集资产

## 01-水泽
地址：https://github.com/0x727/ShuiZe_0x727

## 02-灯塔
地址：https://github.com/TophantTechnology/ARL

## 03-Kunyu
地址：https://github.com/knownsec/Kunyu



# 0x03-优秀项目
```
https://github.com/r0eXpeR/GetInfo
https://github.com/projectdiscovery/uncover -- 包含fofa、shodan、censys
https://github.com/ExpLangcn/WanLi -- 包含fofa、quake
```