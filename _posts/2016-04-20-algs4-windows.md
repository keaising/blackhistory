---
title: 在Windows上安装「算法 第四版」组件
layout: post
guid: 2ef3550f-8cf3-400b-a55b-c512c9af8a1q
tags:
  - Notes

---

这篇日志翻译自[Hello, World in Java on Windows](http://algs4.cs.princeton.edu/windows/)，翻译的原因是[知乎的一个回答](https://www.zhihu.com/question/36491917/answer/67791083)，回答完这个问题之后，得到了广泛的。。嗯。。。私信，私信我如何处理相关问题。惭愧地说，其实我也没有刷完这本书的所有题，但是处理一点入门型的问题好像还可以。但是我也没有精力挨个回复，所以翻译一下官方的回复，应该是够用了。所以说：其实大部分伸手党在伸手之前连官方文档都没有看全_(:з」∠)_

下面我们开始！

——

—— 

这篇文档将向你介绍如何在Windows系统上安装本书将用到的Java开发环境，同时我们也提供了一个手把手的、使用我们提供的DrJava工具或者用命令行来创建、编译和运行你的第一个Java程序的手册，这个过程中用到的所有软件都可以自由下载

本操作指南适用于32位和64位的Windows 8、Windows 7、Vista SP1和XP SP3

——

—— 

## 0. 安装开发环境

我们提供的安装器将会自动下载、安装和配置你将用到的所有开发环境，包括Java SE 7、DrJava、文本库和命令行工具

+  在电脑上登陆以后你会用来写代码的那个Windows账户，这个账户必须具有管理员权限（Administrator）且电脑必须连接到网络。『译者注：以我的经验，你最好还有一个全局翻墙工具，VPN或者Shadowsocks，不然很有可能下载失败』

+ 下载[algs4.exe](http://algs4.cs.princeton.edu/windows/algs4.exe)并双击进行安装，如果在安装开始前你收到一个用户账户控制的警告，点击「是」或者「允许」，如果在安装结束后你收到一个程序兼容性警告，点击「该程序已正确安装」

+ 如果安装成功，你将看到如下两个信息：
    
    * 一个内容这个[运行日志](http://algs4.cs.princeton.edu/windows/log.txt)的命令行窗口
    * 一个内容为蓝色靶心和教科书的标准绘图窗口
    
    需要注意的是：如果你的网络连接较慢的话，安装程序需要持续几分钟甚至更长时间
    
+ 删掉「algs4.exe」

——

—— 

## 1. 在DrJava中创建程序

现在你已经为你的第一个Java程序做好了准备，你将在一个叫DrJava的程序中开发你的Java程序。DrJava包含了语法高亮、匹配括号、自动缩进和显示行号等特性。

* 在上一节中的安装包已经在桌面上创建了DrJava的快捷方式『译者注：如果不慎删掉，还可以在如下目录中找到该程序：C:\Users\Username\algs4』。双击以启动DrJava，如果你收到一个Windows安装警告，点击「允许运行」或者「不禁止」

* 在DrJava的主窗体中，请向下面一样准确无误得输入[HelloWorld.java](http://introcs.cs.princeton.edu/java/11hello/HelloWorld.java.html)中的代码，哪怕你只是漏掉了一个分号，这个程序也不会运行,在你输入的时候，DrJava会为你准备缩进
  {% highlight java %}
  public class HelloWorld {
      public static void main(String[] args) { 
          System.out.println("Hello, World");
      }
  }
  {% endhighlight %}

*  最后，点击「保存」按钮来保存该文件，使用DrJava创建文件夹C:\Users\username\algs4\hello并将文件命名为「HelloWorld.java」，这个文件名是大小写敏感的而且必须匹配Java程序中的类名，其中username是你的Windows用户名

——

—— 

## 2. 在DrJava中编译程序

现在我们来将你的Java代码转化为可以在你的电脑上运行的东西，点击「编译」按钮（Compile），如果一切顺利的话，你会在DrJava底部的编译器输出窗格（Compiler Output Pane）看到这样一条信息

{% highlight java %}
Compilation completed.
{% endhighlight %}

如果DrJava没有编译成功，你应该是输入错了一些东西，重新仔细检查你的代码，你可以用编译器输出窗格中的信息作为参考

——

—— 

## 3. 在DrJava中运行程序

现在来运行你的程序，这是很有趣的部分

+ 在底部的交互窗格（Interactions pane）中输入下列信息，按照习惯，我们高亮了你用粗体输入的部分『译者注：由于博客模板限制我没办法在我这里加粗相应内容，需要看加粗的去看原文吧』

{% highlight java %}
  > java HelloWorld
{% endhighlight %}
  
如果一切顺利，你会看到如下信息：

{% highlight java %}
Welcome to DrJava.  Working directory is C:\Users\username\algs4\hello
> java HelloWorld 
Hello, World
{% endhighlight %}

+ 你或许会在成功运行前重复很多遍「编辑 - 编译 - 运行」的循环

——

—— 

## 4. 命令行界面
