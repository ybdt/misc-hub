# 前言
安全领域四大主流语言JAVA、PHP、GO、Python，对应的好用的IDE：IntelliJ IDEA Ultimate、PhpStorm、GoLand、PyCharm Professional

# 0x01-结论
上述4大IDE的2021.1系列，删除指定目录下的文件夹及修改注册表可重新试用30天

# 0x02-过程
之前发现针对IntelliJ IDEA Ultimate的白嫖方法，由于最近用到GoLand，故联想到之前的方式是否可用于GoLand以及PhpStorm

下图是GoLand 2021.3.2，可看到直接没有免费试用30天的功能  
![image](./pic/01.png)  
而GoLand 2021.1.3则有这个功能，如下图  
![image](./pic/02.png)  
同理PhpStorm 2021.2.3可看到没有免费试用30天的功能，如下图  
![image](./pic/03.png)  
而PhpStorm 2021.1.4则有这个功能（图忘记截了）

我是2022/01/11日下载的30天试用版GoLand，到期日应该是2022/02/10日  
然后在第二天2022/01/12日执行批处理后，到期日变为2022/02/11日  
（其他图忘记截了）只有1个图  
![image](./pic/04.png)

# 0x03-结果
可通过批处理来自动化做这件事情（我个人用PyCharm Community功能目前足够，暂时没测试PyCharm Professional）
```
chcp 65001

rem 参考链接：https://blog.csdn.net/hacker_Lees/article/details/118296294
rem 经测试，此方法针对2021.1系列可用，针对2021.3系列不可用

rem phpstorm
rmdir /s /q C:\Users\ybdt\AppData\Local\JetBrains\PhpStorm2021.1
rmdir /s /q C:\Users\ybdt\AppData\Roaming\JetBrains\PhpStorm2021.1

rem idea
rmdir /s /q C:\Users\ybdt\AppData\Local\JetBrains\IntelliJIdea2021.1
rmdir /s /q C:\Users\ybdt\AppData\Roaming\JetBrains\IntelliJIdea2021.1
reg.exe delete HKEY_CURRENT_USER\SOFTWARE\JavaSoft\Prefs\jetbrains /f

rem pycharm
rmdir /s /q C:\Users\ybdt\AppData\Local\JetBrains\PyCharm2021.1
rmdir /s /q C:\Users\ybdt\AppData\Roaming\JetBrains\PyCharm2021.1

rem goland
rmdir /s /q C:\Users\ybdt\AppData\Local\JetBrains\GoLand2020.3
rmdir /s /q C:\Users\ybdt\AppData\Roaming\JetBrains\GoLand2020.3

pause
```
将上述批处理加到任务计划程序，每月1号定期执行，并设置“过了计划开始时间，立即执行”  

有人竟然问我，如果这个月1号没开电脑怎么办？  
哈哈哈，手动执行一下即可 :)

# 2022/08/06更新  
更方便的方式，安装IDE插件，每次重启IDE后，插件会重新试用（就是说每次重启后都有30天免费试用），且不需要手动操作它  
File -> Settings -> Plugins -> 点击设置的图标 -> Manage Plugin Repositories -> 添加源：https://plugins.zhile.io  
在Marketplace中搜索：reset -> 选择：IDE Eval Reset -> 安装  
Help -> Eval Reset -> 勾选Auto Reset before per restart -> 点击Reset  