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
01-历史IP收集：通过ip138.com查看目标域名解析过的历史IP  
02-ASN收集：当目标组织很大时，可考虑收集目标所在ASN的全部资产  
03-Google Dork收集：收集目标相关的关键字，通过google dork收集目标关联资产  
（这些奇技淫巧目前只有“历史IP收集”在实战中用到过）

# 相关项目
```
01-水泽：https://github.com/0x727/ShuiZe_0x727

02-灯塔：https://github.com/TophantTechnology/ARL

03-Kunyu：https://github.com/knownsec/Kunyu

04-GetInfo：https://github.com/r0eXpeR/GetInfo

05-uncover：https://github.com/projectdiscovery/uncover -- 包含fofa、shodan、censys

06-WanLi：https://github.com/ExpLangcn/WanLi -- 包含fofa、quake
```