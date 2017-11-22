---
title: Hello Git(2)  
date: 2017-11-19 12:15:54  
tags:  
    - GIT  
category: "版本控制"
---
{% cq %}  

Pro Git, Second Edition 读书笔记  

快速上手GIT，学会初始化本地仓库，进行简单的版本管理操作  

本人菜鸟，若发现错误，感激指正~~!  

{% endcq %}  

<!-- more -->
<!-- toc -->

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

## 初始化本地GIT仓库
> 这里假设你知道使用cd,mkdir等基础的常见命令，如果这些都不知道，那你需要去网上搜索并学习一下 。

初始化GIT仓库的指令是:`$ git init`。  

1. 首先，我们要在磁盘上选择一个已存在的目录或新建一个目录当做我们的GIT仓库。   
在F盘新建一个目录GitRepository:
    ```shell
    $ cd f  
    $ mkdir GitRepository  
    $ cd ./GitRepository
    ```  
    ![demo2](http://ouq9v8coj.bkt.clouddn.com/images/gittest2.gif)  
2. 在GitRepository文件夹初始化仓库
    ```shell
    $ git init
    ```  
    ![demo3](http://ouq9v8coj.bkt.clouddn.com/images/gittest3.gif)  
此时我们就成功建立了一个GIT版本控制仓库，在GitRepository文件夹中多了一个.git文件夹，它的作用就是用来跟踪和管理版本库，其余的部分就是工作区间。  

## 基础的版本控制操作  
进行版本控制的目的，就是追踪文件的变更，通过以下流程，就能通过GIT进行版本控制：
  - 对文件进行操作(新增、修改、删除)
  - 查看仓库状态
  - 追踪(暂存)文件
  - 循环前三步
  - 提交追踪(暂存)到版本库  

涉及的操作如下：  
  - `git status`指令可以查看当前文件的状态  
  - `git status -s` or `git stauts -short`指令查看状态简短信息
  - `git diff`指令查看当前工作区与暂存快照的比对
  - `git add`指令添加内容到暂存区，等待下一次提交  
  - `git commit -m "description"`指令提交暂存  

通过以下实例来理解以上操作：  

1. 首先，查看一下仓库的初始化状态，键入`git status`，就能查看当前仓库的状态：  
    ```shell
    $ git status

    On branch master

    No commits yet

    nothing to commit (create/copy files and use "git add" to track)
    ```  
    当前仓库的状态为：目前处于master分支，目前没有提交，仓库没有任何变更。  

    如果键入`git status -s`，则什么都不会显示，表示无任何变化。

2. 在仓库新建一个`test.txt`文本文件,并随便写入一点内容(可以使用系统图形界面直接新建或复制一个文件过来):  
    ```shell
    $ cd /f/GitRepository
    $ vi test.txt
    ```  
    键入`i`进行插入，编辑完成后，按`ESC`后输入`:wq`保存并退出vi编辑器,此时就创建了一个新的test.txt,并且添加了一些文本。假设文本如下:
    ```shell
    Git is the god.
    Nintendo Switch NO.1
    ```  

3. 再次查看当前仓库的状态：  
    ```shell
    $ git status

    On branch master

    No commits yet

    Untracked files:
      (use "git add <file>..." to include in what will be committed)

            test.txt

    nothing added to commit but untracked files present (use "git add" to track)
    ```  
    这里告诉了我们：目前处于master分支，目前没有需要提交的文件，未追踪的文件是`test.txt`。  

    查看简要状态信息：  
    ```shell
    $ git status -s

    ?? test.txt
    ```  
    显示出一个test.txt文件，并且前面带有`??`标记。  
    `??`代表新添加，未跟踪的文件。

4.  要追踪文件变更，需要将文件放入暂存区:  
    ```shell
    $ git add test.txt
    ```  
    查看详细状态：  
    ```shell
    $ git status

    On branch master

    No commits yet

    Changes to be committed:
      (use "git rm --cached <file>..." to unstage)

            new file:   test.txt
    ```  
    这里告诉我们：目前暂存区有一个新建的test.txt等待被提交。  

    查看简要状态信息：  
    ```shell
    $ git status -s

    A  test.txt
    ```  
    显示出一个test.txt文件，并且前面带有`A`标记。  
    `A`代表
