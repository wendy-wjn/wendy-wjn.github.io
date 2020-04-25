第1章	Ubantu安装与配置<p>
一、	认识ubantu<p>
有用，如何下载<p>
二、	虚拟机<p>
1.	分类：<p>
物理机（双系统）；虚拟机（保险）<p>
2.	虚拟机<p>
在宿主机中虚拟出软硬件；相对的客户机，与宿主机完全独立；<p>
虚拟机软件：Vmare、Parallels Desktop、Hyper-V、Virtual Box<p>
手机虚拟机：iTools<p>
三、	Virtual Box安装<p>
1.	网络类型<p>
Nat：虚拟机可访问外网；2个虚拟机之间不可访问；<p>
Nat网络：可访问外网和其他虚拟机；<p>
内部：不能访问外网；<p>
桥接：由外部DHCP时最方便；<p>
第2章	Ubantu基本设置<p>
光盘刻录软件 BuruAware<p>
全盘设定Network->设置<p>
虚拟机镜像分享站点www.osboxes.org/ubantu/Sf.net<p>
一、	操作系统<p>
管理硬件系统（内核）、系统调用运行硬件系统（终端命令）/图形化界面；<p>
类型：桌面/服务器/嵌入式<p>
二、	Linux<p>
版本号（年+月）：普通版本/LTS版本（2年）<p>
熟悉终端：terminal<p>
用户账户默认为标准账号<p>
安装软件：sudo apt-get install name  <p>
卸载软件：sudo apt-get remove name	<p>
更新软件索引目录：sudo apt-get update	<p>
取消：ctrl+c；放大/缩小：ctrl+=/ctrl+-；切换全屏：ctrl+f；自动补全命令和路径：tab键；<p>
yes；bb；cowsay/xcowsay；moo	；cmatrix；aafire；sl；oneko；<p>
第3章	终端命令<p>
一、	文件与目录
分区：Linux系统没有分区概念；Linux目录的组织，只有根目录/<p>
/bin可执行文件<p>
/sbin供超级用户使用的可执行文件<p>
/ect配置文件<p>
eg源地址：/etc/apt/sourse.list<p>
home家目录，给用户存储文件用（1用户->1用户命名文件夹）<p>
收藏夹中的主目录=用户自己的家目录；<p>
可查看主目录各子目录的快捷方式；<p>
/mmt挂载设备用<p>
/boot引导程序<p>
二、	Linux终端命令<p>
1.	ls：列出目录列表名称<p>
-l：详细输出目录信息<p>
-h：人性化方式显示文件大小<p>
-a：显示隐藏文件（以.开始的文件）<p>
2.	cd：进入目录	<p>
cd /（最左侧d为文件夹）<p>
cd .（.：当前目录；..：上一级目录）<p>
cd ~：表示用户自己的家目录；<p>
cd ~=cd/home/lester/<p>
3.	pwd：显示当前工作目录<p>
4.	touch：创建文件<p>
（文件不存在则新建；文件存在则更新创建时间）<p>
5.	mkdir：创建目录<p>
（同级目录用空格间隔 mkdir a b 文件与文件夹不同重名）<p>
（层级目录用-p参数 mkdir a/b））<p>
6.	rmdir：删除空目录，删除内容不进入回收站<p>
7.	rm：删除文件，删除内容不进入回收站<p>
-r：删除非空文件<p>
8.	clear：清屏<p>
9.	cp：复制文件	-格式：cp 源文件路径 目标路径<p>
-r参数，递归复制子目录和文件，只跟目录<p>
10.	mv：移动文件	-格式：mv源文件名 目标路径<p>
-可以用mv重命名文件<p>
-移动子目录和文件，不需要加-r<p>
11.	cat：查看文件内容	-格式：cat 文件名<p>
-参数：-b，对非空行标号<p>
12.	more：查看文件内容（分屏显示）=less	-操作方式：空格下一屏，b上一屏，q退出<p>
13.	grep：搜索	-格式：grep 字符串 文件（字符串中有空格，用引号（单双引号都可））<p>
-n：对搜索出来的结果进行编号<p>
-v：显示不匹配的行<p>
-i：不区分大小写<p>
^：显示以×为行的开头<p>
$：显示以×为行的结尾<p>
14.	echo：显示命令<p>
通常是搭配管道使用：<p>
符号>：输出并覆盖原始内容;将hello word输送到def.txt文件中<p>
符号>>：输出并追加至原始内容<p>
符号|：表示一个命令的输出作为另一命令的输入	实例：ls  -alh ~ | more;ls  -alh ~ | grep P<p>
符号*：任意多字符，包括0<p>
符号?：一个字符<p>
符号[]：表示范围，[abc]表示a,b,c，[a-f].[0-9]<p>
查询帮助	Win：帮助菜单、F1<p>
Linux：-参数：--help（一次性显示所有帮助信息）<p>
-格式：任意终端命令 --help<p>
-命令：man,manual<p>
--格式：man命令（空格下一屏，b上一屏，q退出）<p>
绝对路径：从/开始的路径；cd ~<p>
相对路径：从当前目录开始的路径<p>
三、	远程管理相关命令<p>
1.	<p>
启动终端：Ctrl+Alt+T<p>
Shutdown：默认一分钟关机<p>
shutdown –c：取消：<p>
重启：shutdown -r<p>
定时任务：+num;hh:mm;now（任意数值后关机/重启）<p>
远程管理时尽量不要关机或重启<p>
2.	ifconfig	ifconfig<p>
配合管道命令：Ifconfig | grep inet<p>
3.	ping	默认一直发送数据包<p>
按ctrl+C中止<p>
4.	ssh<p>
基本认识ssh<p>
Linux中非常常用的一个工具，可利用ssh客户端登录ssh服务器<p>
Windows下的Xshell->linux上的ssh服务器<p>
ssh端口：默认22<p>
Windows下的常用的ssh客户端：putty、xshell、secureCRT<p>
ssh客户端<p>
-Linux,Mac所有版本自带ssh <p>
-Windows 7开始自带ssh<p>
ssh远程登录格式 <p>
ssh [-p port] username @ host <p>
username:lester <p>
password:zjnu1234 <p>
host: 192.168.56.1 (NAT=>10.0.2.15) <p>
在linux上安装ssh服务器
安装openssh-server包：sudo apt-get install openssh-server<p>
sudo /etc/init.d/ssh start（启动）<p>
sudo /etc/init.d/ssh stop（关闭）<p>
SSH配置免密码登录<p>
原理：a.生成一个密钥对，在客户机上存放私钥，在服务器上存放公钥；b. 每次登录时，取私钥并与服务器上的公钥配对，配对成功表示认证通过 <p>
步骤：<p>
Q1: 如何生成？ <p>
ssh-keygen(key generator)
根据机器的特征值生成id_rsa，id_rsa.pub （私/公钥）<p>
Q2：生成后的密钥存放在何处？ <p>
存放在用户目录下的.ssh <p>
Q3：服务器如何配置 <p>
任务：id_rsa.pub文件的内容添加到远程主机.ssh目录下的authorized_keys文件 <p>
01、Linux系统中 <p>
ssh-copy-id [-p port] username@host <p>
02、Windows <p>
a. 可视化方式复制 <p>
b. <p>
scp: secure copy，用于远程的安全拷贝 <p>
scp [-P port] 本地文件 username@host：Desktop/01.py <p>
cat id_rsa.pub >~/.ssh/authorized_keys<p>
5.	深入了解计算机网络，特别是NAT<p>
主要有各种情况：<p>
A：桥接网络（家里路由器开通DHCP推荐）<p>
Virtual、host处于同一网段<p>
用ipconfig查出当前的网络<p>
Hostname=inet地址<p>
B：NAT或NAT网络<p>
6.	SCP扩展<p>
远程文件传输的几种方案<p>
1、SCP<p>
2、SCP的扩展应用：WinSCP<p>
3、SFTP:可以理解从SSH通道走的FTP<p>
可以使用的客户端：WinSCP,Filezilla<p>
建议：Windows中使用Chocolatey<p>
1、本地文件上传至服务器 <p>
2、远程文件下载到本地 <p>
任务：将远Desktop下的hello.py下载：scp -P 22 lester@192.168.56.1:Desktop/hello.py hello_world.py <p>
3、将本地文件夹上传至服务器 <p>
scp -r zjnu lester@192.168.56.1:Desktop <p>
4、将远程文件夹下载至本地 <p>
scp -r lester@192.168.56.1:Desktop/01 01_copy<p>
6.	别名登录<p>
给我们访问的远程主机设置一个容易记性的别名；类似于：域名VS IP地址<p>
不同点：域名需要在DNS注册，别名在本机注册<p>
Windows方法：<p>
（1).ssh下新建文件config<p>
（2）config中配置别名<p>
Host ubuntu<p>
HostName 192.168.56.1<p>
User lester<p>
Port 22<p>
（3）别名登录：ssh user@别名<p>
7.	用户权限<p>
ls-l为例<p>
lester@ubuntu:~/Desktop$ ls -lh<p>
总用量 28K<p>
drwxr-xr-x 4 lester lester 4.0K 3月  11 09:51 01<p>
-rw-rw-r-- 1 lester lester   62 4月   1 09:45 config.txt<p>
-rw-r--r-- 1 lester lester  599 3月  11 10:17 def.txt<p>
-rw-r--r-- 1 lester lester  779 3月  11 10:10 hello.py<p>
-rw-rw-r-- 1 lester lester  405 3月  25 09:36 id_rsa.pub<p>
-rw-r--r-- 1 lester lester  599 3月  11 10:19 world.py<p>
drwxrwxr-x 3 lester lester 4.0K 3月  25 09:49 zjnu<p>
依次：权限标识符、硬链接数、用户与组、文件容量、最后修改日期、名称<p>
（1)权限标识符：10位<p>
第一位：d/- （类别，d表示目录-表示文件）<p>
后九位：<p>
-第一组RWX：拥有者的权限<p>
-第二组RWX：所在组的权限<p>
-第三组RWX：其它人的权限<p>
R：可读<p>
W：可写<p>
X：可执行<p>
最大的是：7（三位二进制数转十进制）<p>
最小的是：0（三位二进制数转十进制）<p>
rw-r--r--: 110 100 100（权限掩码）<p>
rwxr-xr-x: 111 101 101<p>
rwxrwxrwx: 777 （Web程序的上传目录）<p>
-----------：000<p>
只读：R--,100，4<p>
读写：RW-,110，6<p>
读取与执行：R-X，101，5<p>
所有权限：7<p>
（2)chmod<p>
格式： <p>
chmod +/- rwx filename/directory<p>
chmod mask filename/directory<p>
示例：文件夹的可执行权限<p>
示例：文件加可执行权限（Python脚本、shell脚本）<p>
8.	超级用户	Linux用户类型：<p>
-root用户：用于系统维护，具有所有权限<p>
-绝大多数的Linux发行版不推荐使用root<p>
-安装时创建的为标准用户<p>
sudo<p>
-su: substitude user替换用户<p>
-预设的身份是root<p>
-需要输入密码，有5分钟有效期<p>
-如果未经授权尝试使用root,会发送警告<p>
用户管理常用命令<p>
创建、删除组（如果不行，可在前面添加sudo）<p>
groupadd；groupdel<p>
tip: 创建新用户时，会自动创建同名用户组<p>
查看组信息	cat /etc/group<p>
修改文件或目录的所在组	sudo chgrp 组名 文件或目录<p>
-默认不修改子目录组信息，要递归修改：chgrp -R 组名 目录名<p>
添加用户（如果不行，可在前面添加sudo）<p>
useradd<p>
-g:设置所在用户组<p>
-m :自动创建家目录<p>
查看用户信息	cat /etc/passwd<p>
cat /etc/passwd | grep 用户名<p>
lester:   x:  1000:  1000:  Lester,,,  :   /home/lester  :/bin/bash<p>
lester:用户名<p>
x:已经设置密码<p>
1000：用户标识<p>
1000: 组标识<p>
Lester: 用户名<p>
/home/lester: 家目录<p>
/bin/bash： 登录时使用的bash<p>
设置用户密码	（如果不行，可在前面添加sudo）<p>
passwd 用户名<p>
不跟用户名，修改自己的密码<p>
删除用户<p>
userdel 用户名；-r: 删除用户时，同时删除家目录<p>
查看id<p>
方法一： cat /etc/passwd | grep 用户名<p>
方法二：id <p>
id 用户名：显示特定用户的标识；id ：显示当前<p>用户的标识<p>
查看当前登录的用户：who：0表示当前终端<p>
查看当前用户的账号名：whoami<p>
解决新建用户无法使用sudo<p>
原理：只有在sudo组，成为成员才可以使用<p>
具有sudo组权限，称为sudoer<p>
usermod更改用户的组信息<p>
sudo usermod -a -G sudo roy<p>
9.	远程修改<p>
场景：需要修改远程主机上的某个文件	解决方案：<p>
a, ssh登录并用nano,vi编辑<p>
b, 先用Scp,winscp等下载文件，再上传文件<p>
在本地的文件编辑器中添加远程编辑的功能<p>
c, 用本地编辑器的远程修改插件<p>
示例：VS Code + Remote SSH <p>
1，在VSCode插件目录中搜索并安装Remote-SSH<p>
2，添加主机，Ctrl +Shift +P， Remote ssh - add a new host，添加后会出现在ssh targets。<p>
3，在主机项上右键，connect ...<p>
4, Open folder，打开远程主机上的某个目录<p>
Extra： VirtualBox中客户机（ubuntu）与主机(win10)的文件共享<p>
1，安装增强功能<p>
点虚拟机菜单中的“安装增强功能”<p>
自动运行光盘中的启动程序<p>
重启虚拟机<p>
2、添加共享文件夹<p>
共享文件夹路径：Win10上的某一个目录<p>
共享文件夹名称：随意<p>
建议选项：自动挂载、固定分配<p>
挂载点：一般放在/media/目录下，如/media/shared<p>
有可能出现的问题，打开挂载点时提示无权限<p>
原因：所用的用户不在vboxsf组<p>
vobxsf: virtual box shared folder<p>
sudo usermod -a -G vboxsf username<p>
第4章	Git应用<p>
一、	Git与Github使用初步<p>
Recap<p>
-SSH架构远程管理的运维体系<p>
-SCP、Remote for VS Code远程编辑<p>
-NAT配置问题<p>
1.	Git版本控制系统（Version Control System, VCS）<p>
其它VCS: CVS, Subersion, Visual source safe<p>
开源共享，可以自架服务器，同时使用客户端访问与应用<p>
专用的第三方的Git服务，相当于租用了别人的Git服务器，在上面创建软件仓库并进行版本管理。<p>
典型的Git服务：Github，Gitlab<p>
2.	Git中的基本概念<p>
-仓库：相当于一个托管的单位，一般对应一个项目<p>
-版本： 仓库中的文件的某一个状态<p>
3.	Git安装	Ubuntu或者Raspbian OS：<p>
apt-get/apt install git<p>
4.	Git的身份认证	一般情况下采用SSH或PGP密钥认证的方式。<p>
参考：SSH的免密登录<p>
5、创建Git仓库	https://github.com/ 注册一个账号<p>
Repositories（仓库）中选择New<p>
仓库地址：<p>
https://github.com/scratchzjnu/zjnumaker.git<p>
git@github.com:scratchzjnu/zjnumaker.git<p>
6、Git初始化配置	提前准备用户名、邮箱：scratchzjnu, service@ilester.net<p>
git config --global user.name "用户名"<p>
git config --global user.email "邮箱”<p>
ssh-keygen -t rsa -C "邮箱"<p>
cat ~/.ssh/id_rsa.pub并将输出的内容添加到Github账户/setttings/ssh and gpg keys<p>
7、初始化仓库	创建一个用作本地存储的仓库目录<p>
git init（会初始化仓库，相关配置在.git下）<p>
注意：.git文件尽量不要修改<p>
8、将文件添加到仓库并提交	前置：创建一个文件，例如：readme.md<p>
git add readme.md<p>
git commit -am "开发日志"<p>
git status<p>
9、查看文件的版本记录	git log 文件名查看<p>
commit 后面的标识即为版本号<p>
10、回退版本	git checkout 版本号 文件名<p>
git <p>
11、将文件上传到Git服务器	前置：需要找到Git仓库地址，配置好SSH或GPG密钥<p>
git remote add origin github上的地址<p>
git push –u origin master<p>
12、通常操作	单用户： <p>
本地修改文件<p>
git add <p>
git commit <p>
git push <p>

