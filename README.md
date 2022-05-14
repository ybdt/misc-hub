# 闲言碎语
HW比拼的一个维度就是速度，看谁先发现弱资产，所以自动化资产收集很重要，Web资产收集基本不外乎这4类：子域名、Web路径、全端口、供应链，具体见下面介绍

口子的质量很大程度影响打内网的质量，应先检测离目标最近的资产，来快速打下比较正的点，实在没点可打，再逐渐扩大范围，由此，我的Web打点顺序通常是
```
01：子域名 -> 指纹识别  
02：子域名 + Web路径 -> 指纹识别  
03：全端口 -> 指纹识别  
04：全端口 + Web路径 -> 指纹识别  
05：供应链 -> 指纹识别  
06：供应链 + Web路径 -> 指纹识别  
```
将上述过程用你熟悉的语言实现自动化

# 01-子域名
```
01-通过fofa收集子域：https://fofa.info/
02-通过OneForAll收集子域：https://github.com/shmilylty/OneForAll
```
# 02-Web路径
```
01-通过dirsearch扫描Web路径：https://github.com/maurosoria/dirsearch
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
```
01-历史IP收集：通过ip138.com查看目标域名解析过的历史IP  
02-ASN收集：当目标组织很大时，可考虑收集目标所在ASN的全部资产  
03-Google Dork收集：收集目标相关的关键字，通过google dork收集目标关联资产  
（这些奇技淫巧目前只有“历史IP收集”在实战中用到过）  
```

# 自动化资产收集项目
```
01-水泽：https://github.com/0x727/ShuiZe_0x727
02-灯塔：https://github.com/TophantTechnology/ARL
03-Kunyu：https://github.com/knownsec/Kunyu
04-GetInfo：https://github.com/r0eXpeR/GetInfo
05-uncover：https://github.com/projectdiscovery/uncover -- 包含fofa、shodan、censys
```

# 通常都是无点时，再回来过一边信息收集:)
```
https://github.com/r0eXpeR/GetInfo
https://qftm.github.io/Information_Collection_Handbook/
https://lovebear.top/info/cn/index.html
```

# todo-list
```
将团队内部指纹库、开源的指纹库、自动化指纹识别工具内的指纹库做一个汇总
```

# 闲言碎语
很多时候收集到有效资产但不能识别到对应指纹，其实跟没收集到资产效果是一样的，所以指纹识别很重要

# 01-指纹识别
```
使用团队内部开发的自动化指纹识别工具
```

# 在线指纹识别网站
```
01-whatweb：http://whatweb.bugscaner.com/look/

02-云悉：https://www.yunsee.cn/

03-TideSec：http://finger.tidesec.com/

04-360Finger-P：https://fp.shuziguanxing.com
```

# 自动化指纹识别项目
```
01-Finger：https://github.com/EASY233/Finger

02-dismap：https://github.com/zhzyker/dismap

03-httpx：https://github.com/projectdiscovery/httpx

04-AlliN：https://github.com/P1-Team/AlliN

05-ObserverWard：https://github.com/0x727/ObserverWard
```

# 指纹库项目
```
01-EHole(棱洞)：https://github.com/ShiHuang-ESec/EHole

02-EHole(棱洞)3.0：https://github.com/EdgeSecurityTeam/EHole

03-whatweb-plus：https://github.com/winezer0/whatweb-plus

04-fingerprint：https://github.com/r0eXpeR/fingerprint
```