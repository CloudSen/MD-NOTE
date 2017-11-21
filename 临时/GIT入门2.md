> 本节将带你体验GIT，你能学会如何创建本地仓库，并进行简单的使用  

## 本节名词
- repository: 仓库(GIT目录)，它就是电脑中的某个目录，在这个目录里面的文件都可以被GIT所管理，你每次对文件新增、删除、修改的历史记录，都会保存在这。

## 安装完GIT后简单的设置
安装完毕后，打开GIT-BASH,键入以下指令，进行一个简单的设置，现在不用关心这是做什么的，后面会有详细的讲解。
```shell
$ git config --global user.name = "你的名字"
$ git config --global user.email = "你的邮箱"
```
![demo1](http://ouq9v8coj.bkt.clouddn.com/images/gittest1.gif)  
没有消息的消息，就是好消息。依次键入以上指令后，界面没有报任何错误，说明设置成功了~！

## 新建本地GIT仓库
> 这里假设你知道使用cd,mkdir等基础的常见命令，如果这些都不知道，那你需要去网上搜索并学习一下 。

初始化GIT仓库的指令是:`$ git init`。  

1. 首先，我们要在磁盘上选择一个已存在的目录或新建一个目录当做我们的GIT仓库。   
在F盘新建一个目录GitRepository:
    ```shell
    $ cd f  
    $ mkdir GitRepository  
    $ cd ./GitRepository
    ```
2. 在GitRepository文件夹初始化仓库
    ```shell
    $ git init
    ```  
![demo2](http://ouq9v8coj.bkt.clouddn.com/images/gittest2.gif)  
![demo3](http://ouq9v8coj.bkt.clouddn.com/images/gittest3.gif)  
此时我们就成功建立了一个GIT版本控制仓库，在GitRepository文件夹中多了一个.git文件夹，它的作用就是用来跟踪和管理版本库。  

## GIT初尝试
有了GIT仓库后，我们就可以把文件放入仓库，进行版本控制了。  

1. 首先在仓库新建一个`test.txt`文本文件,并随便写入一点内容(可以使用系统图形界面直接新建或复制一个文件过来):  
    ```shell
    $ cd /f/GitRepository
    $ vi test.txt
    ```  
    键入`i`进行插入，编辑完成后，按`ESC`后输入`:wq`保存并退出vi编辑器,此时就创建了一个新的test.txt,并且添加了一些文本。假设文本如下:
    ```
    Git is the god.
    Nintendo Switch NO.1
    ```

2. 现在仓库里有了文件，但是还差一步才能对它进行版本控制：  
    ```shell
    $ git add test.txt
    $ git commit -m "新建了test.txt文本"
    ```  
