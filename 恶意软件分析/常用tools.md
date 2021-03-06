## 常用tools

### 行为分析(动态分析)
#### autoruns
用于启动项管理，可以制作快照，在恶意软件前后进行对比。

#### regshot
RegShot是个小巧的注册表静态比较工具，它能快速地帮助您发现注册表的变化，甚至通过扫描硬盘来让您掌握硬盘上某些文件夹\[或是整个硬盘\]的改变！

也就是用来对比注册表变化

#### handlediff.exe
Tool to detect changes to the handle tables of all processes on a system (useful to analyze the side-effects of code injecting malware)

用来查看**系统句柄表**是否更改的工具。

#### CaptureBat.exe
win32系统下，进行行为分析的工具。用来监控系统状态。

#### fakenet
FakeNet-NG是一款专为恶意软件分析人员以及渗透测试专家设计的下一代动态网络分析工具

该工具可以在模拟合法网络服务的过程中拦截/重定向所有的或特定的网络流量。在FakeNet-NG的帮助下，恶意软件分析专家可以迅速识别恶意软件的功能并捕捉到网络签名。

#### procdot
是个恶意软件分析软件，只要把process monitor导出的文件(process monitor需要选中thread column)，和wireshark保存的log文件(capp格式),把两种log丢进去，它就能绘制出恶意软件的执行流程图。

#### REMnux
这个工具也要**注意**。它是一个**基于 Ubuntu 专为逆向解析恶意软件开发的 Linux 发行版**

REMnux 发行介质是 **VMware 虚拟机**，当然你也可以用 VirtualBox 来打开，默认的用户名和密码分别是"remnux" 和"malware"，用户**无法使用 root 用户登录**，必须登录后使用 sudo 来操作，它使用了 Enlightenment 窗口环境。

REMnux内置了很多进行恶意软件分析的工具，本质就是一个linux发行版。

### 静态分析

#### PEiD
著名的查壳工具，可以拿来查看程序有没有被加壳，并可能检测出具体的加壳程序。

直接将文件拖进去就可以执行

#### BinText
静态分析程序中的字符串。

#### FileAlyzer
FileAlyzer是一款**文件分析程序**.FileAlyzer允许对文件的**基本分析**(显示文件特性和文件内容以**十六进制形式存储**)并且能解释象资源结构的普通文件内容**(象文本、图表、HTML、媒介和PE).使用FileAlyzer用鼠标右键单击您想要分析的文件就可以像观看正常物品一样简单的分析查看文件.

#### Stud_PE
很强大的**PE工具**，可以查看和修改 EXE、DLL等**PE结构文件的PE结构**。PE工具，用来学习PE格式十分方便。

#### PeStudio
也是一个PE文件分析工具。
