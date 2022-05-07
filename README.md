# 闲言碎语
HW比拼的一个维度就是速度，看谁先发现弱资产，所以自动化（资产收集--指纹识别--漏洞检测--口令检测）很重要

口子的质量很大程度影响打内网的质量，所以先检测离目标最近的资产，来快速打下比较正的点，实在没点可打，再逐渐扩大范围，由此，我的Web打点顺序通常是：  
子域名 + We路径  
上述无可打点 -> 公网IP段及全端口 + Web路径  
上述无可打点 -> 子公司-兄弟公司-父公司-供应商 + Web路径  
通常，在“子公司-兄弟公司-父公司-供应商 + Web路径”环节都会有点，不过资产可能会偏  

将上述过程用你熟悉的语言实现自动化

# 01-子域名
```
01-通过fofa收集子域：https://fofa.info/

02-通过OneForAll收集子域：https://github.com/shmilylty/OneForAll
```
# 02-Web路径
```
01-通过dirsearch扫描Web目录：https://github.com/maurosoria/dirsearch

02-通过ffuf扫描Web目录：https://github.com/ffuf/ffuf
```
# 03-全端口
```
01-通过收集到的子域名及IP等信息，分析目标可能的公网ip段，并通过nmap扫描全端口：https://nmap.org/
```
# 04-供应链
```
02-通过ENScan_GO自动化收集（子公司-兄弟公司-父公司-供应商）相关信息：https://github.com/wgpsec/ENScan_GO
```

# 05-奇技淫巧
01-历史IP收集：通过ip138.com查看目标域名解析过的历史IP  
02-ASN收集：当目标组织很大时，可考虑收集目标所在ASN的全部资产  
03-Google Dork收集：收集目标相关的关键字，通过google dork收集目标关联资产  
```
这些奇技淫巧目前只有“历史IP收集”在实战中用到过
```

# 相关项目
```
01-水泽：https://github.com/0x727/ShuiZe_0x727

02-灯塔：https://github.com/TophantTechnology/ARL

03-Kunyu：https://github.com/knownsec/Kunyu

04-GetInfo：https://github.com/r0eXpeR/GetInfo

05-uncover：https://github.com/projectdiscovery/uncover -- 包含fofa、shodan、censys

06-WanLi：https://github.com/ExpLangcn/WanLi -- 包含fofa、quake
```