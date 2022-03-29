# 0x01-资产收集
0x01-父子公司收集
```
通过天眼查、企查查收集目标父子公司

可通过ENScan自动化收集目标父子公司
```
0x02-根域收集
```
通过“ICP/IP地址/域名信息备案管理系统”（https://beian.miit.gov.cn/#/Integrated/index）收集目标根域
```
0x03-子域收集
```
通过OneForAll收集子域：https://github.com/shmilylty/OneForAll
通过esd收集子域：https://github.com/FeeiCN/ESD
```
0x04-C段收集
```
ping目标域名获取ip（用于非CDN情况）

fofa收集目标子域，通过查看子域对应IP，可推测目标的大概C段
```
0x05-旁站收集
```
目标未使用CDN时，可通过nmap扫描目标全端口，查看开放哪些其他端口，通过其他端口切入
```
0x06-ASN收集
```
当目标组织较大时，可考虑收集目标所在ASN的全部资产
```
0x07-历史IP收集
```
通过ip138.com查看目标域名解析过的历史IP
```
0x08-Google Dork收集
```
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