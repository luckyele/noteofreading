# 关于Python的几本书


## No1:《简明Python教程》

最早看到的是《简明Python教程》，电子版中有www.linuxidc.com字样，应该是从linux公社下载到的。

记得就是看着这个教程，写过一个爬虫程序，完成从指定网站的网页栏目自动抓取全部新闻的标题。那是一个不完善的程序，没有用到数据库，只是把新闻标题以及相应链接，逐个保存在本地文本文件中。遇到的主要问题是编码转换问题。

全书只有98页16章，特点正是简洁，涵盖了Python的各种基本知识，很多内容只是轻轻一点，但对于初学者来说却容易接受。

全书包括以下章节：
* 第01章 介绍Python
* 第02章 安装Python
* 第03章 最初的步骤
* 第04章 基本概念
* 第05章 运算符与表达式
* 第06章 控制流（if,for,while)
* 第07章 函数
* 第08章 模块，介绍模块的概念。
* 第09章 数据结构，介绍了如何使用列表、元组和字典。
* 第10章 脚本编写案例（文档保存）
* 第11章 面向对象的编程
* 第12章 输入/输出。
* 第13章 处理异常

try...except语句处理异常；
raise语句引发异常（需要指明错误或异常的名称，以及触发对象，应该是一个Error或Exception类的直接或间接导出类）；
try...finally语句，必须要做的操作可放在finally块中，

* 第14章 

介绍Python标准库，介绍了sys,os模块，其他模块功能可以查标准文档。

* 第15章

更多python的内容，包括：
特殊方法，《Python参考手册》中可以找到这个大列表。
列表综合，也就是把更多的列表操作组合在一起使用。如[x*2 for x in list if x > 2 ]，将list列表中大于2的元素扩大为原来的2倍。
在函数中接收元组和列表，分别使用*、\**前缀。这种方法在函数需要获取可变数量的参数时特别有用。
lambda形式，创建新的函数对象，并在动行时返回。
exec语句   执行字符串或文件中的Python语句
eval语句   计算字符串的有效Python表达式
assert语句 声明某个条件是真，失败时引发AssertionError。
repr语句   反引号可完成相同的功能，取得对象的规范字符串表示

* 第16章

提出一个练习题，即用Python编写一个命令行版的通讯录管理程序，还介绍了几个使用Python的GUI库，包括：
PyQt，这是Qt工具包的Python绑定，Qt工具包是KDE的基石，内容参看《使用Python语言的GUI编程：Qt版》。
PyGTK，是GTK+工具包的Python绑定，GTK+是GNOME的基石，内容参看官方主页。
wxPython，是wxWidgets工具包的Python绑定，可移植性好，多平台运行。
TkInter，历史悠久的GUI工具包，IDLE就是一个TkInter程序，是标准Python发行版的一部分。

如何选择GUI库，作者认为可以考虑三个因素，即是否付费，运行环境，以及用户GUI类型（KDE 或GNOME）。作者还强烈建议开始大型Python程序开发前要浏览Python标准文档。

利用其他编程语言的功能库，Python还有其他一些实现。如：Jython，Java实现的Python解释器，稳定成熟，可用Python编写程序同时使用Java库。IronPython，C#实现的Python解释器。Lython，Python的Lisp的实现。

资源：
1）Python.org
2）comp.lang.python
3）《Python 实用大全》
4）《迷人的Python》 David Mertz
5）《深入理解Python》 <-- 这本书作者建议作为第二本。
6） Daily Python-URL!
7） Vaults of Parnassus
8） ONLamp.com Python DevCenter
9） dirtSimple.org
10) Python Notes

Python读标准输入
raw_input() 从标准输入读取一行，并返回一个字符串（去掉结尾的换行符）
input()  与raw_input()基本可以互换，但假设输入是有效的表达式，并返回运算结果。

## No2: 《深入理解Python》

《深入理解Python》是前面一本书作者推荐的，应该是一本比较经典的python入门书。

全书共18章，第1章先讲python在各种系统上的安装，包括：windows,Mac OS, RedHat Linux，Debian GNU/Linux。还讲到如何从源代码安装Python.

第2章以一段代码为例介绍Python程序的构成，这里特别使用与其他编程语言做对比的方法，以帮助有其他编程语言背景的读者快速理解python。

python是依据sys.path中的目录逐个搜索导入模块。在python中一切都是对象。

测试模块的方法：因为python模块都是对象，可以利用对象的属性（所有的模块都有一个内置属性__name__,如果import模块，__name__为模块的文件名；如果是直接运行模块，__name__的值将缺省为__main__）对模块进行测试。方法是:
>  if __name__ == "__main__":
> 	<test code>

第3章谈到内置数据类型

Dictionary，即键值对， 形如：D = {key1:value1, key2:value2}，键值不可重复。Dictionary是无序的，大小写敏感的。键可为字符串、整数等。del 删除字典元素，如del D[key1]；D.clear() 清除所有元素。

List 是python中使用最频繁的数据类型，形如：li = [index], index可以为负数；li[a:b]，表示按顺序从a开始直到但不包括b的所有元素。也可以简写，如li[:3],或li[2:]；还可以按步长切片，如li[::-1]，表示步长为-1，从最后一个元素开始前切片，即倒置列表。

增加元素，用append()，insert()，extend()等。其中append可增加不同类型的元素，extend是将一个list中的元素加到原list中。

index("元素名")，返回第一个出现的索引。可以用in判断某个元素是否是list中，如：if i in list，其返回True或False。

删除元素用remove()，pop()删除列表最后一个元素并返回，类似于stack。

list可以接运算符+,+=, *等。

Tuple,即元素不可变的list，同样可以切片，切片会得到一个新的tuple.如：a = ("a","b","c")。

关于变量。python中的变量可以不加声明直接使用，但是不能不赋值。可以一次赋多值，也可以连续赋值。

可以使用多变量赋值创建返回多个值的函数，只要返回一个包含所有值的tuple即可。

映射list，在《简明python》对这种操作称为列表综合。
"？".join(字符串列表) 将字符串列表的元素依次连接为一个字符串，并用"?"分隔。

s.split("?") 用"?" 将字符串s，分割为列表。
s.split("?",x) x可以指定分割次数；x=1时，取分隔符之前的部分，常用。

第4章，本章被译为自省的威力。没看到英文版，直觉认为这里有些别扭。

dir(__builtins__) 列出python内置函数。

## 关于网页源码转码：chardet

windows cmd shell 输出的是cp936编码
linux终端输出的是utf-8编码
python自带的IDLE在windows下使用的是cp936编码

系统的缺省编码(一般就是ascii)：sys.getdefaultencoding() 

系统当前的编码：locale.getdefaultlocale() 

系统代码中临时被更改的编码（通过locale.setlocale(locale.LC_ALL,“zh_CN.UTF-8″)）：locale.getlocale() 

文件系统的编码：sys.getfilesystemencoding() 

终端的输入编码：sys.stdin.encoding 

终端的输出编码：sys.stdout.encoding 

代码的缺省编码：文件头上# -*- coding: utf-8 –*-

> from urllib.request import urlopen
> import  chardet

> response=urlopen(url,timeout=3)
> html_byte=response.read()
> chardit1 = chardet.detect(html_byte)
> file = open(PROJECT_NAME + '/' + str(ALLNUM) + '.html', 'wb')  
> html_string=html_byte.decode(chardit1['encoding']).encode('utf-8')
> file.write(html_string)
> file.close()

s.decode('gbk2312','ignore').encode('utf-8')
用ignore参数忽略非法字符。

>>> from urllib2 import urlopen
>>> for line in urlopen('http://www.ahwh.gov.cn'):
...     line = line.decode('gb2312','ignore').encode('utf-8')
...     if 'charset' in line:
...             print line
... 
> <meta http-equiv="Content-Type" content="text/html; charset=gb2312" />

os库
getcwd()
chdir()
system('mkdir today')
针对日常的文件和目录管理任务，shutil模块
