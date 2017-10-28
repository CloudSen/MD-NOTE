# GIT

## 一、安装后的配置  
1. 设置个人信息  
	```
	$git config --global user.name "CloudSen"  
	$git config --global user.email "www.402645063@gmail.com"
	```
2. 提交检出均不转换换行符，拒绝提交包含混合换行符的文件
	```
	$git config --global core.autocrlf false
	$git config --global core.safecrlf true
	```  
2. 创建仓库  
	```
	创建一个空文件夹
	$cd /f  
	$mkdir GitRepository  
	$cd /f/GitRepository
	```
	```
	在此文件夹初始化仓库
	$git init
	```
	此时，在GitRepository仓库文件夹中多了一个.git文件夹，用来跟踪管理版本库。  
3. 测试一下GIT  
	```
	在仓库新建一个test文件夹，并新建test.txt文本文档:
	$cd /f/GitRepository
	$mkdir test
	$cd ./test
	$vi test.txt
	```  
	键入i进行插入，编辑完成后，按ESC后输入:wq保存并退出vi编辑器,  
	此时就创建了一个新的test.txt
	```
	将test.txt加入版本控制:  
	
	```