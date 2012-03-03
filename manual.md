Giti.me User Manual
===================

准备工作
--------
- Windows用户：下载并安装最新版本的[Git for Windows](http://code.google.com/p/msysgit/downloads/list)
- Linux，OSX用户：安装git，例如：Ubuntu用户请在Terminal运行`sudo apt-get install git`

建立Giti.me服务
----------------
Windows用户请在Git Bash中完成操作，Linux和OSX用户请在Terminal中完成操作。

1.  检查是否已经生成了SSH Key  
	`$ cd ~/.ssh`
	
	如果显示"No such file or directory"请跳到步骤2，否则跳到步骤3。
	
2.  生成新的SSH Key  
	执行如下命令以生成新的SSH Key  
	`$ ssh-keygen -t rsa -C "yourname@youremail.com"`  
	正确填写保存目录和passphrase。（建议不修改默认目录，即第一个填写项直接回车以设为默认值）
	
3.	上传SSH Key到Giti.me  
	登录Giti.me，选择添加SSH Key。将您生成好的SSH Key复制到标识为key的文本框中，并为它起一个标题。最后点击Add Key以保存SSH Key。
	
4.	测试一下  
	运行`$ ssh -T git@github`，若您看到了欢迎信息和版本库授权信息，则说明您的配置成功了。
	
5.	设置个人信息  
	运行如下命令来修改您的名字和email  
	`git config --global user.name "Your Name"`  
	`git config --global user.name your_email@youremail.com`  

建立一个新的版本库
------------------
1.	初始化git版本库，添加README文件  
	运行如下指令将建立一个新git版本库并新建一个README文件。  
	`$ mkdir repo`  
	`$ cd repo`  
	`$ git init`  
	`$ touch README`
	
2.	提交修改  
	运行如下指令将提交README文件到服务器  
	`$ git add README`  
	`$ git commit -m "first commit"`  
    `$ git remote add origin git@giti.me:username/repo.git`  
	`$ git push origin master`
	
用户命令速查
---------------
* 	运行如下指令可以查询您可访问的版本库以及授权信息  
	`ssh git@giti.me expand`
*	运行如下指令可以查询您的系统授权  
	`ssh git@giti.me info`
*	git常用命令速查  
[![Git命令速查](cheatsheet.png)](cheatsheet.png)
