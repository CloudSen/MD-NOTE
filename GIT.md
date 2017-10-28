# GIT

## 一、安装后的配置  
1. 设置个人信息 git config  
	```
	$ git config --global user.name "CloudSen"  
	$ git config --global user.email "www.402645063@gmail.com"
	```
2. 提交检出均不转换换行符，拒绝提交包含混合换行符的文件
	```
	$ git config --global core.autocrlf false
	$ git config --global core.safecrlf true
	```  
3. 创建仓库git init  
	```
	创建一个空文件夹
	$ cd /f  
	$ mkdir GitRepository  
	$ cd /f/GitRepository
	```
	```
	在此文件夹初始化仓库
	$ git init
	```
	此时，在GitRepository仓库文件夹中多了一个.git文件夹，用来跟踪管理版本库。  
4. 测试一下GIT  
	```
	在仓库新建一个test文件夹，并新建test.txt文本文档:
	$ cd /f/GitRepository
	$ mkdir test
	$ cd ./test
	$ vi test.txt
	```  
	键入i进行插入，编辑完成后，按ESC后输入:wq保存并退出vi编辑器,  
	此时就创建了一个新的test.txt
	```
	将test.txt加入版本控制(待提交):  
	$ git add test.txt  
	提交test.txt:
	$ git commit -m "新建了test文本"
	```
	此时会显示出更改的内容：
	修改了1个文件，新增了2行
	```
	[master (root-commit) 0058b79] 新建了test文本  
	1 file changed, 2 insertions(+)
	create mode 100644 test/test.txt
	```
  
# 二、基本命令
1. `$ git init` 初始化一个代码仓库；
2. `$ git add <files>` 添加文件到待提交列表；
3. `$ git commit -m "your comment"` 将待提交的文件，提交到仓库，并添加注释；
4. `$ git status`查看仓库当前状态，哪些文件被修改了，还有哪些准备提交的更改；
5. `$ git diff`查看更改详情，新增哪些行，删除了哪些行；