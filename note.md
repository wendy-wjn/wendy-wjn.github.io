第1章	Ubantu安装与配置
一、	认识ubantu
有用，如何下载
二、	虚拟机
1.	分类：
物理机（双系统）；虚拟机（保险）
2.	虚拟机
在宿主机中虚拟出软硬件；相对的客户机，与宿主机完全独立；
虚拟机软件：Vmare、Parallels Desktop、Hyper-V、Virtual Box
手机虚拟机：iTools
三、	Virtual Box安装
1.	网络类型
Nat：虚拟机可访问外网；2个虚拟机之间不可访问；
Nat网络：可访问外网和其他虚拟机；
内部：不能访问外网；
桥接：由外部DHCP时最方便；
第2章	Ubantu基本设置
光盘刻录软件 BuruAware
全盘设定Network->设置
虚拟机镜像分享站点www.osboxes.org/ubantu/Sf.net
一、	操作系统
管理硬件系统（内核）、系统调用运行硬件系统（终端命令）/图形化界面；
类型：桌面/服务器/嵌入式
二、	Linux
版本号（年+月）：普通版本/LTS版本（2年）
熟悉终端：terminal
用户账户默认为标准账号
安装软件：sudo apt-get install name  
卸载软件：sudo apt-get remove name	
更新软件索引目录：sudo apt-get update	
取消：ctrl+c；放大/缩小：ctrl+=/ctrl+-；切换全屏：ctrl+f；自动补全命令和路径：tab键；
yes；bb；cowsay/xcowsay；moo	；cmatrix；aafire；sl；oneko；
第3章	终端命令
一、	文件与目录
分区：Linux系统没有分区概念；Linux目录的组织，只有根目录/
/bin可执行文件
/sbin供超级用户使用的可执行文件
/ect配置文件
eg源地址：/etc/apt/sourse.list
home家目录，给用户存储文件用（1用户->1用户命名文件夹）
收藏夹中的主目录=用户自己的家目录；
可查看主目录各子目录的快捷方式；
/mmt挂载设备用
/boot引导程序
二、	Linux终端命令
1.	ls：列出目录列表名称
-l：详细输出目录信息
-h：人性化方式显示文件大小
-a：显示隐藏文件（以.开始的文件）
2.	cd：进入目录	
cd /（最左侧d为文件夹）
cd .（.：当前目录；..：上一级目录）
cd ~：表示用户自己的家目录；
cd ~=cd/home/lester/
3.	pwd：显示当前工作目录
4.	touch：创建文件
（文件不存在则新建；文件存在则更新创建时间）
5.	mkdir：创建目录
（同级目录用空格间隔 mkdir a b 文件与文件夹不同重名）
（层级目录用-p参数 mkdir a/b））
6.	rmdir：删除空目录，删除内容不进入回收站
7.	rm：删除文件，删除内容不进入回收站
-r：删除非空文件
8.	clear：清屏
9.	cp：复制文件	-格式：cp 源文件路径 目标路径
-r参数，递归复制子目录和文件，只跟目录
10.	mv：移动文件	-格式：mv源文件名 目标路径
-可以用mv重命名文件
-移动子目录和文件，不需要加-r
11.	cat：查看文件内容	-格式：cat 文件名
-参数：-b，对非空行标号
12.	more：查看文件内容（分屏显示）=less	-操作方式：空格下一屏，b上一屏，q退出
13.	grep：搜索	-格式：grep 字符串 文件（字符串中有空格，用引号（单双引号都可））
-n：对搜索出来的结果进行编号
-v：显示不匹配的行
-i：不区分大小写
^：显示以×为行的开头
$：显示以×为行的结尾
14.	echo：显示命令
通常是搭配管道使用：
>：重定向，输出并覆盖原始内容;将hello word输送到def.txt文件中
>>：输出并追加至原始内容
|：表示一个命令的输出作为另一命令的输入	实例：ls  -alh ~ | more;ls  -alh ~ | grep P
*：任意多字符，包括0
?：一个字符
[]：表示范围，[abc]表示a,b,c，[a-f].[0-9]
查询帮助	Win：帮助菜单、F1
Linux：-参数：--help（一次性显示所有帮助信息）
-格式：任意终端命令 --help
-命令：man,manual
--格式：man命令（空格下一屏，b上一屏，q退出）
绝对路径：从/开始的路径；cd ~
相对路径：从当前目录开始的路径
三、	远程管理相关命令
1.	
启动终端：Ctrl+Alt+T
Shutdown：默认一分钟关机
shutdown –c：取消：
重启：shutdown -r
定时任务：+num;hh:mm;now（任意数值后关机/重启）
远程管理时尽量不要关机或重启
2.	ifconfig	ifconfig
配合管道命令：Ifconfig | grep inet
3.	ping	默认一直发送数据包
按ctrl+C中止
4.	ssh
基本认识ssh
Linux中非常常用的一个工具，可利用ssh客户端登录ssh服务器
Windows下的Xshell->linux上的ssh服务器
ssh端口：默认22
Windows下的常用的ssh客户端：putty、xshell、secureCRT
ssh客户端
-Linux,Mac所有版本自带ssh 
-Windows 7开始自带ssh
ssh远程登录格式 
ssh [-p port] username @ host 
username:lester 
password:zjnu1234 
host: 192.168.56.1 (NAT=>10.0.2.15) 
在linux上安装ssh服务器
安装openssh-server包：sudo apt-get install openssh-server
sudo /etc/init.d/ssh start（启动）
sudo /etc/init.d/ssh stop（关闭）
SSH配置免密码登录
原理：a.生成一个密钥对，在客户机上存放私钥，在服务器上存放公钥；b. 每次登录时，取私钥并与服务器上的公钥配对，配对成功表示认证通过 
步骤：
Q1: 如何生成？ 
ssh-keygen(key generator)
根据机器的特征值生成id_rsa，id_rsa.pub （私/公钥）
Q2：生成后的密钥存放在何处？ 
存放在用户目录下的.ssh 
Q3：服务器如何配置 
任务：id_rsa.pub文件的内容添加到远程主机.ssh目录下的authorized_keys文件 
01、Linux系统中 
ssh-copy-id [-p port] username@host 
02、Windows 
a. 可视化方式复制 
b. 
scp: secure copy，用于远程的安全拷贝 
scp [-P port] 本地文件 username@host：Desktop/01.py 
cat id_rsa.pub >~/.ssh/authorized_keys
5.	深入了解计算机网络，特别是NAT
主要有各种情况：
A：桥接网络（家里路由器开通DHCP推荐）
Virtual、host处于同一网段
用ipconfig查出当前的网络
Hostname=inet地址
B：NAT或NAT网络
6.	SCP扩展
远程文件传输的几种方案
1、SCP
2、SCP的扩展应用：WinSCP
3、SFTP:可以理解从SSH通道走的FTP
可以使用的客户端：WinSCP,Filezilla
建议：Windows中使用Chocolatey
1、本地文件上传至服务器 
2、远程文件下载到本地 
任务：将远Desktop下的hello.py下载：scp -P 22 lester@192.168.56.1:Desktop/hello.py hello_world.py 
3、将本地文件夹上传至服务器 
scp -r zjnu lester@192.168.56.1:Desktop 
4、将远程文件夹下载至本地 
scp -r lester@192.168.56.1:Desktop/01 01_copy
6.	别名登录
给我们访问的远程主机设置一个容易记性的别名；类似于：域名VS IP地址
不同点：域名需要在DNS注册，别名在本机注册
Windows方法：
（1).ssh下新建文件config
（2）config中配置别名
Host ubuntu
HostName 192.168.56.1
User lester
Port 22
（3）别名登录：ssh user@别名
7.	用户权限
ls-l为例
lester@ubuntu:~/Desktop$ ls -lh
总用量 28K
drwxr-xr-x 4 lester lester 4.0K 3月  11 09:51 01
-rw-rw-r-- 1 lester lester   62 4月   1 09:45 config.txt
-rw-r--r-- 1 lester lester  599 3月  11 10:17 def.txt
-rw-r--r-- 1 lester lester  779 3月  11 10:10 hello.py
-rw-rw-r-- 1 lester lester  405 3月  25 09:36 id_rsa.pub
-rw-r--r-- 1 lester lester  599 3月  11 10:19 world.py
drwxrwxr-x 3 lester lester 4.0K 3月  25 09:49 zjnu
依次：权限标识符、硬链接数、用户与组、文件容量、最后修改日期、名称
（1)权限标识符：10位
第一位：d/- （类别，d表示目录-表示文件）
后九位：
-第一组RWX：拥有者的权限
-第二组RWX：所在组的权限
-第三组RWX：其它人的权限
R：可读
W：可写
X：可执行
最大的是：7（三位二进制数转十进制）
最小的是：0（三位二进制数转十进制）
rw-r--r--: 110 100 100（权限掩码）
rwxr-xr-x: 111 101 101
rwxrwxrwx: 777 （Web程序的上传目录）
-----------：000
只读：R--,100，4
读写：RW-,110，6
读取与执行：R-X，101，5
所有权限：7
（2)chmod
格式： 
chmod +/- rwx filename/directory
chmod mask filename/directory
示例：文件夹的可执行权限
示例：文件加可执行权限（Python脚本、shell脚本）
8.	超级用户	Linux用户类型：
-root用户：用于系统维护，具有所有权限
-绝大多数的Linux发行版不推荐使用root
-安装时创建的为标准用户
sudo
-su: substitude user替换用户
-预设的身份是root
-需要输入密码，有5分钟有效期
-如果未经授权尝试使用root,会发送警告
用户管理常用命令
创建、删除组（如果不行，可在前面添加sudo）
groupadd；groupdel
tip: 创建新用户时，会自动创建同名用户组
查看组信息	cat /etc/group
修改文件或目录的所在组	sudo chgrp 组名 文件或目录
-默认不修改子目录组信息，要递归修改：chgrp -R 组名 目录名
添加用户（如果不行，可在前面添加sudo）
useradd
-g:设置所在用户组
-m :自动创建家目录
查看用户信息	cat /etc/passwd
cat /etc/passwd | grep 用户名
lester:   x:  1000:  1000:  Lester,,,  :   /home/lester  :/bin/bash
lester:用户名
x:已经设置密码
1000：用户标识
1000: 组标识
Lester: 用户名
/home/lester: 家目录
/bin/bash： 登录时使用的bash
设置用户密码	（如果不行，可在前面添加sudo）
passwd 用户名
不跟用户名，修改自己的密码
删除用户
userdel 用户名；-r: 删除用户时，同时删除家目录
查看id
方法一： cat /etc/passwd | grep 用户名
方法二：id 
id 用户名：显示特定用户的标识；id ：显示当前用户的标识
查看当前登录的用户：who：0表示当前终端
查看当前用户的账号名：whoami
解决新建用户无法使用sudo
原理：只有在sudo组，成为成员才可以使用
具有sudo组权限，称为sudoer
usermod更改用户的组信息
sudo usermod -a -G sudo roy
9.	远程修改
场景：需要修改远程主机上的某个文件	解决方案：
a, ssh登录并用nano,vi编辑
b, 先用Scp,winscp等下载文件，再上传文件
在本地的文件编辑器中添加远程编辑的功能
c, 用本地编辑器的远程修改插件
示例：VS Code + Remote SSH 
1，在VSCode插件目录中搜索并安装Remote-SSH
2，添加主机，Ctrl +Shift +P， Remote ssh - add a new host，添加后会出现在ssh targets。
3，在主机项上右键，connect ...
4, Open folder，打开远程主机上的某个目录
Extra： VirtualBox中客户机（ubuntu）与主机(win10)的文件共享
1，安装增强功能
点虚拟机菜单中的“安装增强功能”
自动运行光盘中的启动程序
重启虚拟机
2、添加共享文件夹
共享文件夹路径：Win10上的某一个目录
共享文件夹名称：随意
建议选项：自动挂载、固定分配
挂载点：一般放在/media/目录下，如/media/shared
有可能出现的问题，打开挂载点时提示无权限
原因：所用的用户不在vboxsf组
vobxsf: virtual box shared folder
sudo usermod -a -G vboxsf username
第4章	Git应用
一、	Git与Github使用初步
Recap
-SSH架构远程管理的运维体系
-SCP、Remote for VS Code远程编辑
-NAT配置问题
1.	Git版本控制系统（Version Control System, VCS）
其它VCS: CVS, Subersion, Visual source safe
开源共享，可以自架服务器，同时使用客户端访问与应用
专用的第三方的Git服务，相当于租用了别人的Git服务器，在上面创建软件仓库并进行版本管理。
典型的Git服务：Github，Gitlab
2.	Git中的基本概念
-仓库：相当于一个托管的单位，一般对应一个项目
-版本： 仓库中的文件的某一个状态
3.	Git安装	Ubuntu或者Raspbian OS：
apt-get/apt install git
4.	Git的身份认证	一般情况下采用SSH或PGP密钥认证的方式。
参考：SSH的免密登录
5、创建Git仓库	https://github.com/ 注册一个账号
Repositories（仓库）中选择New
仓库地址：
https://github.com/scratchzjnu/zjnumaker.git
git@github.com:scratchzjnu/zjnumaker.git
6、Git初始化配置	提前准备用户名、邮箱：scratchzjnu, service@ilester.net
git config --global user.name "用户名"
git config --global user.email "邮箱”
ssh-keygen -t rsa -C "邮箱"
cat ~/.ssh/id_rsa.pub并将输出的内容添加到Github账户/setttings/ssh and gpg keys
7、初始化仓库	创建一个用作本地存储的仓库目录
git init（会初始化仓库，相关配置在.git下）
注意：.git文件尽量不要修改
8、将文件添加到仓库并提交	前置：创建一个文件，例如：readme.md
git add readme.md
git commit -am "开发日志"
git status
9、查看文件的版本记录	git log 文件名查看
commit 后面的标识即为版本号
10、回退版本	git checkout 版本号 文件名
git 
11、将文件上传到Git服务器	前置：需要找到Git仓库地址，配置好SSH或GPG密钥
git remote add origin github上的地址
git push –u origin master
12、通常操作	单用户： 
本地修改文件
git add 
git commit 
git push 

