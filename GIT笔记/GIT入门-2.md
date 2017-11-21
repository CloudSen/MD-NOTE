---
title: GIT入门(2)  
date: 2017-11-19 12:15:54  
tags:  
  - GIT  
category: "版本控制"
---
{% cq %}  

Pro Git, Second Edition 读书笔记  

初次安装GIT后需要进行的配置详解  

本人菜鸟，若发现错误，感激指正~~!  

{% endcq %}  
<!-- toc -->
![git](http://ouq9v8coj.bkt.clouddn.com/images/GIT%E5%85%A5%E9%97%A82-1.jpg)  
  
# GIT入门(2)——首次配置
## 配置详解
通过**git config**工具来配置GIT环境，通过它我们能获得和设置配置变量。  
GIT的配置变量存储在三个不同的位置：  

对于Linux系统:    

传入参数|配置变量的位置|解释|优先级
:----|:----|:----|:----
"--system"|/etc/gitconfig|包含了系统中所有用户及其仓库|低
"--global"|~/.gitconfig 或 ~/.config/git/config| 针对当前PC登录者|中
无参|git/config| 针对当前仓库|高
对于Windows系统：  
可以通过在GIT BASH中键入`git config --list --show-origin`来查看各个配置属性的存放位置：  
![demo1](http://ouq9v8coj.bkt.clouddn.com/images/GIT%E5%85%A5%E9%97%A82-2.gif)  
由上方表格可知，GIT的配置文件在不同域具有不同的优先级，git config 会选择优先级较高的配置。  
<!-- more -->  
## 常用的配置变量
变量名|作用|建议值
:----|:----|:----
user.name|提交者名字|自定
user.email|提交者邮箱|自定
core.editor|文本编辑器|vim
core.autocrlf|自动转换换行符|false
core.safecrlf|是否禁止提交混合换行符的文件|true  
使用git config 依次进行设置(添加`--global`后，当前用户不管在系统中执行什么操作都会使用这些配置参数):  
{% codeblock 参数配置 lang:shell %}
$ git config --global user.name "CloudSen"
$ git config --global user.email "www.402645063@gmail.com"
$ git config --global core.editor "vim"
$ git config --core.autocrlf false
$ git config --core.autosafecrlf true
{% endcodeblock %}  
![demo2](http://ouq9v8coj.bkt.clouddn.com/images/GIT%E5%85%A5%E9%97%A82-3.gif)  
正所谓没有消息，就是最好的消息。如果一次键入以上配置后，没有任何提示信息，那么就表示设置成功了~！  
{% note info %}  
编辑器按自己喜好定，可以是emacs、vi、notepad++等。  
Windows的回车换行符是CRLF，而UNIX使用的LF，两者是不兼容的。 
类似的历史问题还有Windows的反斜杠(反人类)。  
{% endnote %}
{% note warning %}  
GIT的换行符转换机制还存在bug，有时会出现意想不到的问题，因此建议不使用GIT的自动转换，并且禁止提交包含混合换行符的文件。
{% endnote %}  
## 检查配置项
设置好配置项后通过`--list`参数，来列出当前GIT可以找到的所有配置：  
{% codeblock 参数配置 lang:shell %}
$ git config --list  
{% endcodeblock %}  
也可以查看某个具体的配置项：  
{% codeblock 参数配置 lang:shell %}
$ git config --get <配置变量名>
{% endcodeblock %}  
![demo3](http://ouq9v8coj.bkt.clouddn.com/images/GIT%E5%85%A5%E9%97%A82-4.gif)    
若同一个配置变量被打印出多次，说明这个变量在不同的域中进行了设置，GIT会使用最后打印出的那个值。  
## 删除配置项  
使用`--unset`参数来删除配置项：  
{% codeblock 参数配置 lang:shell %}
$ git config --unset <配置变量名>
{% endcodeblock %}  

> 至此，已经对GIT有了一个初步的了解，并配置好了身份信息，接下来马上开始GIT的基础知识。