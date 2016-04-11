
### linux目录结构   
* /    		根目录   
* /boot 	系统启动目录   
* /dev		外部设备   
* /etc		配置文件   
* /home		用户主目录   
* /lib		库文件目录   
* /usr		
* /var 		动态文件目录   
* /proc 	虚拟文件目录   

### linux启动过程简介    
power on-> BIOS -> HD -> boot looder -> grub —> kernel boot -> init ... login   
http://www.ruanyifeng.com/blog/2013/08/linux_boot_process.html　　　

### 理解Linux下的一些概念    
* Linux下的命令都是相应的程序，例如C语言程序和shell脚本程序，可以用whereis命令查看   
* 配置文件的或者目录前面都有.，例如.bashrc , .vimrc , .ssh    
* 一般不要用root账户登录系统，可以给普通用户超级管理员权限，即sudo，在centos下操作用一下的命令		
```
	$ su 	//切换到root用户    
	# vi /etc/sudoers     //修改sudo权限的配置文件
	//找到root	ALL=(ALL)	ALL这一行，然后在下面插入一行，和这行一样，就是需该成自己的用户名即可，然后保存退出   
```    

### Linux常用命令   
```
	ls 			//显示某个目录下面的目录，后面可以跟具体的路径，如ls /etc    
	ll 			//等价于ls -al，或者ls -l,在 .bashrc目录下，找到alias 设置的别名就可以看见和修改   
	ln 			//设置软链接等，和设置环境变量相似     
	cp 			//复制文件，cp ./a.txt  /home/user/  第一个是要复制的文件，第二个是复制到何处    
	mv 			//相当于win下的剪切然后粘贴   参数和上一条命令相似    
	rm			//删除文件或者目录，rm a.txt  是删除这个文件，删除目录要加上-rf参数，表示递归删除这个目录下的所有东西  rm -rf ./java/   
	tar 		//解压tar.gz 文件，要加上参数 ，一般为 -zxvf   
	zip,unzip	//解压zip文件   

	ssh 		//后面加上地址，用于远程登录 
	ssh-keygen -t rsa 	//用于生成sshkey，用于远程登录和推送文件用，使用之后会在当前用户的家目录下生成.ssh文件，内部的在配置Hadoop的时候见过   
	scp 		//向其他的主机或者服务器推送文件     

``` 

### vim常识   
vim是一个在命令行中的编辑器，在终端中也可以用简称vi启动   
* vim有三种模式，分别是命令模式，插入模式，视图模式   
* 在命令模式按i进入插入模式，然后就可以正常编辑   
* 在启动vim之后就是命令模式，在插入模式按esc可以进入命令模式，在命令模式按v可以进入视图模式     
* 视图模式就是自己选择要操作的文字，可以自己尝试     
* vim的配置文件在用户家目录下的.vimrc ,	可以自己在内部写上常用的配置，然后拷在U盘随身携带一用好多年   
### vim常用命令			
* i 	//在光标前面插入    
* I 	//在当前行的最前面开始插入   
* a 	//在光标的后面开始插入   
* A 	//在当前行的最后开始插入    
* o 	//在下一行开始输入    
* O 	//在上一行插入一行空白，同时开始输入   
* .		//执行上一次的操作     
* dd 	//删除当前行     
* yy 	//复制当前行    
* p 	//粘贴上一次复制或者删除的内容     
* G 	//直接跳转到之后一行    
* gg	//直接跳转到第一行    
以上操作都是在命令模式中的操作，下面介绍三个常用的设置命令,在命令模式下先打上:
* :set number 		//显示行号   
* :set nonumber 	//取消行号
* :set tabstop=4 	//设置tab键的宽度是4    
其他的用到的话在找百度    

### Linux包管理工具        

* 包管理工具提供软件包和软件的安装，升级，卸载，常见的包管理如下，具体使用自己查    
* apt-get 		//debian系的Linux常用,如debian，Ubuntu，deepin    
* yum 			//redhat系的Linux常用,如redhat，centOS    
* pacman 		//archlinux的包管理    
* npm/apm 		//nodejs 提供的包管理，很常用，需要提前安装nodejs    


```自己看看就好，有不对的地方请指正，不要拿到外面去丢人，哈哈```
