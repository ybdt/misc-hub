收集顺序按照红队Web打点顺序，先收集离目标最近的资产，越来越远...

# 0x01-旁站收集
```
先通过本地ping及多地ping判断目标是否使用CDN

未使用CDN时
先通过空间测绘快速获取目标开放的全部端口（这一步不多余，HW比的就是谁先发现脆弱资产），同时通过nmap扫描目标全端口，查看是否开放其他端口
```
# 0x02-子域收集
```
通过FOFA收集子域：https://fofa.info/
通过OneForAll收集子域：https://github.com/shmilylty/OneForAll
通过esd收集子域：https://github.com/FeeiCN/ESD
```
# 0x03-C段收集
```
由旁站收集步骤获知目标是否使用CDN

未使用CDN时
通过收集到的子域，推测目标IP段为C段、半个C段、半个B段...

使用CDN时
通过收集到的子域，推测目标的大概C段
```
# 0x04-根域收集
```
通过“ICP/IP地址/域名信息备案管理系统”（https://beian.miit.gov.cn/#/Integrated/index）收集目标根域
```
# 0x05-父子公司收集
```
通过天眼查、企查查收集目标父子公司

可通过ENScan自动化收集目标父子公司
```
# 0x06-ASN收集
```
当目标组织较大时，可考虑收集目标所在ASN的全部资产
```
# 0x07-历史IP收集
```
通过ip138.com查看目标域名解析过的历史IP
```
# 0x08-Google Dork收集
```
收集目标相关的关键字，通过google dork收集目标关联资产

google dork:
https://blog.csdn.net/u014565127/article/details/53842885
https://blog.csdn.net/u014565127/article/details/53868443
allintitle:毕节 电网 系统
program site:google.com
```

# 0x02-同类项目
```
https://github.com/r0eXpeR/GetInfo
https://github.com/projectdiscovery/uncover -- 包含fofa、shodan、censys
https://github.com/ExpLangcn/WanLi -- 包含fofa、quake
```

# 0x02-指纹识别
在线指纹识别平台
```
http://whatweb.bugscaner.com/look/
https://www.yunsee.cn/
http://finger.tidesec.com/
https://scan.top15.cn/web/
https://fp.shuziguanxing.com/#/
```
优秀项目
```
https://github.com/ShiHuang-ESec/EHole
https://github.com/EdgeSecurityTeam/EHole
https://github.com/winezer0/whatweb-plus
https://github.com/r0eXpeR/fingerprint
```