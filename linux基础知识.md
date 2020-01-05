<!-- TOC -->

- [# 隐藏文件](#%e9%9a%90%e8%97%8f%e6%96%87%e4%bb%b6)
- [# 相对路径与绝对路径](#%e7%9b%b8%e5%af%b9%e8%b7%af%e5%be%84%e4%b8%8e%e7%bb%9d%e5%af%b9%e8%b7%af%e5%be%84)
- [# Linux常用命令](#linux%e5%b8%b8%e7%94%a8%e5%91%bd%e4%bb%a4)
- [ls（list，列表）](#lslist%e5%88%97%e8%a1%a8)
- [cd（change directory，更改目录）](#cdchange-directory%e6%9b%b4%e6%94%b9%e7%9b%ae%e5%bd%95)
- [pwd（print work directory，打印工作目录）](#pwdprint-work-directory%e6%89%93%e5%8d%b0%e5%b7%a5%e4%bd%9c%e7%9b%ae%e5%bd%95)
- [mkdir（make directory，创建文件夹）](#mkdirmake-directory%e5%88%9b%e5%bb%ba%e6%96%87%e4%bb%b6%e5%a4%b9)
- [mv（move，移动）](#mvmove%e7%a7%bb%e5%8a%a8)
- [touch](#touch)
- [cp（copy，复制）](#cpcopy%e5%a4%8d%e5%88%b6)
- [rm（remove，去除，删除）](#rmremove%e5%8e%bb%e9%99%a4%e5%88%a0%e9%99%a4)
- [cat](#cat)
- [rmdir（remove directory，删除文件夹）](#rmdirremove-directory%e5%88%a0%e9%99%a4%e6%96%87%e4%bb%b6%e5%a4%b9)
- [ln（link，连接文件）](#lnlink%e8%bf%9e%e6%8e%a5%e6%96%87%e4%bb%b6)
- [man](#man)
- [apt-get](#apt-get)
- [# 编辑器vi的使用](#%e7%bc%96%e8%be%91%e5%99%a8vi%e7%9a%84%e4%bd%bf%e7%94%a8)
- [vi基础使用](#vi%e5%9f%ba%e7%a1%80%e4%bd%bf%e7%94%a8)
- [vi的高级使用](#vi%e7%9a%84%e9%ab%98%e7%ba%a7%e4%bd%bf%e7%94%a8)
	- [查找](#%e6%9f%a5%e6%89%be)
	- [快速切换行](#%e5%bf%ab%e9%80%9f%e5%88%87%e6%8d%a2%e8%a1%8c)
	- [设置显示行号](#%e8%ae%be%e7%bd%ae%e6%98%be%e7%a4%ba%e8%a1%8c%e5%8f%b7)
	- [行删除](#%e8%a1%8c%e5%88%a0%e9%99%a4)
	- [行复制粘贴](#%e8%a1%8c%e5%a4%8d%e5%88%b6%e7%b2%98%e8%b4%b4)
- [# linux中权限表示&管理](#linux%e4%b8%ad%e6%9d%83%e9%99%90%e8%a1%a8%e7%a4%ba%e7%ae%a1%e7%90%86)
- [普通用户与特权用户](#%e6%99%ae%e9%80%9a%e7%94%a8%e6%88%b7%e4%b8%8e%e7%89%b9%e6%9d%83%e7%94%a8%e6%88%b7)
- [rwx与权限表示](#rwx%e4%b8%8e%e6%9d%83%e9%99%90%e8%a1%a8%e7%a4%ba)
- [# 进阶](#%e8%bf%9b%e9%98%b6)
- [find](#find)
- [grep](#grep)
- [which和whereis](#which%e5%92%8cwhereis)
- [uname](#uname)
- [开机和关机](#%e5%bc%80%e6%9c%ba%e5%92%8c%e5%85%b3%e6%9c%ba)
- [tree/lstree](#treelstree)
- [mount/umount](#mountumount)
- [磁盘空间相关](#%e7%a3%81%e7%9b%98%e7%a9%ba%e9%97%b4%e7%9b%b8%e5%85%b3)
- [用户管理](#%e7%94%a8%e6%88%b7%e7%ae%a1%e7%90%86)
- [权限管理](#%e6%9d%83%e9%99%90%e7%ae%a1%e7%90%86)
- [文件打包压缩与解压缩](#%e6%96%87%e4%bb%b6%e6%89%93%e5%8c%85%e5%8e%8b%e7%bc%a9%e4%b8%8e%e8%a7%a3%e5%8e%8b%e7%bc%a9)
- [sed和awk](#sed%e5%92%8cawk)
- [格式化文件系统](#%e6%a0%bc%e5%bc%8f%e5%8c%96%e6%96%87%e4%bb%b6%e7%b3%bb%e7%bb%9f)

<!-- /TOC -->





# Linux的目录结构



# 隐藏文件

---
linux中隐藏文件特点是文件名以.开头，跟文件属性无关。在linux中查看隐藏文件用ls -a命令（普通显示ls）

# 相对路径与绝对路径
---
什么是路径：路径是用来标识一个文件在操作系统的文件系统中存储位置的。pathname
> 举例：
> 全路径（pathname）D:\winshare\enum.c
> 路径（path）D:\winshare			 	
> 文件名（name）enum.c				

**绝对路径：**路径是从绝对位置开始的。譬如Windows中从某一个盘符开始（C:\），linux中从根目录/开始
**相对路径：**指明路径的时候，是从当前所在的位置开始的。
> 举例：
> D:\我的文档\123\123.txt
> D:\我的文档\abc\abc.txt
> 当前在123.txt，但是要去abc.txt
> 方式1：采用绝对路径。D:\我的文档\abc\abc.txt
> 方式2：采用相对路径。../abc/abc.txt
> 从当前路径开始，往上走一层，再往下走一层（abc）就到了

> 测试：
> /abc/123/def.txt	是linux绝对路径	
> abc/123/def.txt		不是linux绝对路径
> F:\abc\123\def.txt	是windows绝对路径
> abc\123\def.txt		不是windows绝对路径

# Linux常用命令
---
## ls（list，列表）
作用：使用列表把当前文件夹下所有文件显示出来
> ls -a	显示所有文件，包括隐藏文件
> ls -l	以详细信息显示
> ls -a -l
> ls -l -a
> ls -la
> ls -al	四种方式都是可以的

> ls -l显示的详细信息中：
> -rw-r--r--
> drwxr-xr-x
> 一共10个字符，第一个字符表示文件类型，后面9个字符表示文件权限。
> 文件类型：
> "-" 表示普通文件。普通文件指文本文件和二进制文件，如a.c  1.txt a.out都是普通文件
> d 表示文件夹，d是directory的缩写
> l 表示符号连接文件，后面会用->打印出它指向的文件
> s 表示socket文件
> p 表示管道文件 pipe

## cd（change directory，更改目录）
作用：用来切换目录
涉及到相对路径和绝对路径 
> cd ..		
> ..代表上一层目录
> .代表当前目录

## pwd（print work directory，打印工作目录）
作用：打印出当前的绝对路径

## mkdir（make directory，创建文件夹）
作用：创建空文件夹
> mkdir -p 级联创建文件夹

## mv（move，移动）
作用：在目录间移动文件，重命名文件
> mv 源文件pathname 目的文件pathname

## touch
作用：创建空文件
> touch pathname

## cp（copy，复制）
作用：复制文件或文件夹
> cp 源文件pathname 目标文件pathname
> cp -r 用来复制文件夹
> cp -f 强制复制
> 实际操作时，一般都是cp -f复制文件，
> cp -rf复制文件夹

## rm（remove，去除，删除）
作用：用来删除文件，文件夹
> rm 文件pathname
> rm -r 文件夹pathname（递归删除）
> rm -f 文件（强制删除）

## cat
作用：直接在命令行下显示文件内容
	
## rmdir（remove directory，删除文件夹）
作用：删除空文件夹
> rmdir和rm -r的区别：rmdir只能删除空文件夹，而rm -r可以删除空文件夹和非空文件夹

## ln（link，连接文件）
基础：windows中快捷方式，实际上快捷方式和它指向的文件是独立的两个文件，两个都占硬盘空间，只不过用户访问快捷方式时，其效果等同于访问指向的文件。		

linux中有两种连接文件：
一种叫软连接（符号连接），等同于windows中快捷方式
一种叫硬连接
创建软连接文件： ln -s 源文件名 符号连接文件名
> 举例：ln -s src.c，linker.c，	linker.c就是src.c的一个符号连接文件

硬连接：ln 源文件名 连接文件名
> 硬连接实际上和源文件在硬盘中是同一个东西，效果类似于硬盘上的一个文件，在文件系统上，在我们看来有好多个文件一样。每次删除一个文件时，只要他还有其他的硬连接存在，这个文件就不会被真正删除。只有等所有的连接文件都删除掉了，这个文件才会被真正从硬盘上删除。

## man
作用：查询man手册，获得帮助信息
> man 1 ls		1表示查询的是linux命令
> man 2 xxx		2表示查询的是linux api
> man 3 xxx		3表示查询的是C库函数
> 注意：在man手册中查询时，退出按Q键（Q就是quit的缩写）

## apt-get
作用：在ubuntu中用来在线安装、卸载软件的程序
> apt-get install vim
> apt-get remove vim
> 注意，安装和卸载都是在线的，也就是说ubuntu必须能上网才能使用apt-get 

**说明：**apt-get 安装软件的原理和必要性。
linux操作系统的发行版，内核版本，定制性，造成了linux中软件的不兼容性。在linux中安装软件是一件困难的事情，装了软件能不能用不一定。ubuntu解决了这个问题，ubuntu就适合某个发行版（ubuntu10.04）的所有软件做了一个列表，然后用户通过apt-get install的方式安装软件，就会实时连接到ubuntu服务器，服务器会根据你的ubuntu版本，给你下载合适的软件来安装。这样确保了软件的兼容性。



# 网络通讯命令

## ifconfig  显示或设置网络设备

- ifconfig  显示网络设备

- ifconfig eth0 up 启用eth0网卡

- ifconfig eth0 down  停用eth0网卡

## ping   探测网络是否通畅

- ping 192.168.0.1

## netstat 查看网络端口

- netstat -an | grep 3306 查询3306端口占用情况



# 系统管理命令

## df 显示磁盘信息

- df –h  友好显示大小

- free 显示内存状态

## clear 清屏幕

## ps 正在运行的某个进程的状态

- ps –ef  查看所有进程

- ps –ef | grep ssh 查找某一进程

## kill 杀掉某一进程

- kill 2868  杀掉2868编号的进程

- kill -9 2868  强制杀死进程

## who 显示目前登入系统的用户信息

## hostname 查看当前主机名

## uname 显示系统信息

- uname -a 显示本机详细信息。

> 依次为：内核名称(类别)，主机名，内核版本号，内核版本，内核编译日期，硬件名，处理器类型，硬件平台类型，操作系统名称



## 开机和关机

shutdown -h now		立即关机
init 0				关机
shutdown -r now		立即重启
reboot				重启



# 编辑器vi的使用
---
> 什么是编辑器？编辑器就是一款软件，它的主要作用就是用来编辑。譬如编写文件，编写代码。
> Windows中的常用编辑器，如自带的notepad。比较好用的notepad++，UltraEditor，SlickEditor
> Linux中常用编辑器，自带的最古老的vi。比较好用的vim，gedit。
> 注：vi和vim的关系：vim是vi的升级版，推荐使用vim。
> 我们在后面提到vi时，其实都是指vim。

## vi基础使用
使用vi来打开/创建一个文件
> vi pathname

**vi的两种模式：**
命令模式：当vi打开时默认为命令模式，要转入输入模式，**需要按a或者i键。**在命令模式下，键盘上输入的所有东西都被vi当作命令来对待。在输入模式下**按ESC键退回**到命令模式。

> 在命令模式下，最好不要乱输入。此时应该输入相应的命令，来让vi做相应的事。
> 输入模式：输入模式用来向文件输入内容。可以从命令模式中按a或者i进入输入模式。进入输入模式后，就可以随意按键盘进行输入了。输入完成后如果要保存，要先退回到命令模式（因为保存也是一种命令）。
> <br/>注：注意看屏幕左下角，当命令模式时无提示信息或者提示文件名等信息，等处于输入模式时，提示 -- INSERT --

在命令模式下如何保存：
:wq			保存并且退出
:w			只保存不推出
:q			不保存退出		进来看了一下没改退出
:q!			不保存强制退出
:wq!		保存并强制退出

## vi的高级使用
### 查找
在命令模式下，输入/xxx，就可以查找到xxx

### 快速切换行
在命令模式下，输入:num，就可以快速切换到num行

### 设置显示行号
在命令模式下，输入:set nu，就可以显示行号
> 注：设置不显示行号，命令模式输入:set nonu
> 设置永久显示行号，需要修改vi的配置文件。打开vi的配置文件~/.vimrc，在其中输入set nu即可。

### 行删除
命令模式下，先将光标移动到要删除的行，然后输入dd
如果要删除连续多行，譬如要删除连续的3行，使用3dd 

### 行复制粘贴
复制：命令模式下，nyy
粘贴：命令模式下，p
> 细节，复制时要把光标放在多行的第一行，粘贴时实际粘贴到当前光标所在行的下一行。

# linux中用户和权限管理
---
## 普通用户与特权用户 
> su命令切换用户

Windows中有普通用户和特权用户，特权用户是Administrator，普通用户可以有很多个。
特权用户是系统的管理员，对系统内所有文件具有操作权限。每个普通用户只能处理自己的文件，不能访问其他用户的文件，更不能随意处理操作系统的文件。
Linux中也有普通用户和特权用户的区别。特权用户就是root用户。普通用户权限受到限制，譬如说普通用户不能cd /root，普通用户不能使用apt-get install 来装软件。	

**可以使用su 用户名来在不同用户间切换。譬如要从普通
用户切换到root，可以su root，然后输入root的密码即可转入root用户。从root要切换到普通用户gec，则su gec即可。**



## 用户管理

useradd user1	添加一个名为user1的用户
userdel	user1	删除一个名为user1的用户
passwd user1	为名为user的用户设置密码
adduser user1	添加一个名为user1的用户，同时创建宿主目录，用户shell等。
**adduser和useradd的区别：**
adduser是一个脚本，而useradd是一个二进制应用程序。adduser创建用户时比较麻烦，但是一次设定完所有的信息；而useradd设置时简单，但是需要额外的设置宿主目录，密码那些信息。



## 权限管理

作用：用来管理系统中文件的权限。
	chmod （change mode）修改文件权限，比较常用，要记得
	chown （change owner，修改属主）
	chgrp （change group，修改文件的组）
	
ls -l 列出的属性，显示详细信息
-rwxr-xr-x
一共10个字符，第一个表示文件属性（d表示文件夹，-表示普通文件），剩下的9个分成三组。每组中三个分别表示r可读w可写x可执行。如果是字母表示有这个权限，如果是-表示没这个权限。三组分别表示：第一组表示文件属主的权限，第二组表示属主所在的组用户的权限，第三组表示其他用户的权限。

权限还有另一种表示方法，用数字来表示。
编码规则如下：
r	可读		4
w	可写		2
x	可执行		1
-无权限		0

有了这个编码规则，则 rwxr-xr-x  编码后为755

第一种修改权限的方法：
要把权限改成	rwxr--r--	则对应的编码值为744
修改命令为：chmod 744 文件名

第二种修改权限的方法：
在原来的权限基础上进行修改，即增加或减少某权限。
三个组用户的编码依次为： 属主u	属主所在的组g	其他用户o
譬如
要属主增加可执行权限	chmod u+x 文件名
其他用户增加可写权限	chmod o+w 文件名
属主所在组用户去掉可执行权限	chmod g-x 文件名 

# 进阶
---
## find
功能：在linux文件系统中，用来查找一个文件放在哪里了。
举例：find /etc -name "interfaces"
总结：
(1)什么时候用find？ 
当你知道你要找的文件名，但是你忘记了它被放在哪个目录下，要找到该文件时，用find。
(2)怎么用find？
**find 路径 -name "文件名"**

## grep
功能：在一个文本文件中，查找某个词。
举例：grep -nr "SUN" *
总结：
(1)什么时候用grep？
当你想查找某个符号在哪些地方（有可能是一个文件，也有可能是多个文件组成的文件夹）出现过，就用grep
(2)怎么用？
	grep -nr "要查找的符号" 要查找的目录或文件集合
注意：-n表示查找结果中显示行号，-r表示要递归查找

## which和whereis
功能：查找一个**应用程序（二进制文件）**在哪里
举例：which ls 		whereis ls
区别
	which只显示二进制文件的路径
	whereis显示二进制文件的路径，和其源码或man手册位置



## tree/lstree	
功能：显示文件和目录由根目录开始的树形结构
	
## mount/umount
功能：用来挂载磁盘到文件系统中
举例：mount -t nfs -o nolock 192.168.1.141:/root/rootfs /mnt	挂载
	  umount /mnt 卸载


## 磁盘空间相关
df -h	显示已挂载的分区列表
du -h	列出文件或文件夹的大小
du -h 文件名，可以列出这个文件有多大，列出方式是以人比较好看懂的方式。不像 ls -l列出的都是以字节为单位。


	
	




​	
## 文件打包压缩与解压缩
tar -czvf dir.tar.gz dir/		将dir目录打包成dir.tar.gz
tar -cjvf dir.tar.bz2 dir/		将dir目录打包成dir.tar.bz2
tar -zxvf dir.tar.gz 			解压缩dir.tar.gz
tar -jxvf dir.tar.bz2			解压缩dir.tar.bz2
	
	
## sed和awk
正则表达式。匹配加替换。


## 格式化文件系统
mkfs	/dev/hd1
mkfs -t vfat 32 -F /dev/hd1		创建一个FAT32文件系统





​		