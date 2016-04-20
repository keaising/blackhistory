---
title: 在Windows上安装「算法 第四版」组件
layout: post
guid: 2ef3550f-8cf3-400b-a55b-c512c9af8a1q
tags:
  - Notes

---

这篇日志翻译自[Hello, World in Java on Windows](http://algs4.cs.princeton.edu/windows/)，翻译的原因是[知乎的一个回答](https://www.zhihu.com/question/36491917/answer/67791083)，回答完这个问题之后，得到了广泛的。。嗯。。。私信，私信我如何处理相关问题。惭愧地说，其实我也没有刷完这本书的所有题，但是处理一点入门型的问题好像还可以。但是我也没有精力挨个回复，所以翻译一下官方的回复，应该是够用了。所以说：其实大部分伸手党在伸手之前连官方文档都没有看全_(:з」∠)_

下面我们开始！

这篇文档将向你介绍如何在Windows系统上安装本书将用到的Java开发环境，同时我们也提供了一个手把手的、使用我们提供的DrJava工具或者用命令行来创建、编译和运行你的第一个Java程序的手册，这个过程中用到的所有软件都可以自由下载

本操作指南适用于32位和64位的Windows 8、Windows 7、Vista SP1和XP SP3

## 0. 安装开发环境

我们提供的安装器将会自动下载、安装和配置你将用到的所有开发环境，包括Java SE 7、DrJava、文本库和命令行工具

1. 在电脑上登陆以后你会用来写代码的那个Windows账户，这个账户必须具有管理员权限（Administrator）且电脑必须连接到网络。『译者注：以我的经验，你最好还有一个全局翻墙工具，VPN或者Shadowsocks，不然很有可能下载失败』

2. 下载[algs4.exe](http://algs4.cs.princeton.edu/windows/algs4.exe)并双击进行安装，如果在安装开始前你收到一个用户账户控制的警告，点击「是」或者「允许」，如果在安装结束后你收到一个程序兼容性警告，点击「该程序已正确安装」

3. 如果安装成功，你将看到如下两个信息：
    
    * 一个内容这个[运行日志](http://algs4.cs.princeton.edu/windows/log.txt)的命令行窗口
    * 一个内容为蓝色靶心和教科书的标准绘图窗口
    
    需要注意的是：如果你的网络连接较慢的话，安装程序需要持续几分钟甚至更长时间
    
4. 删掉「algs4.exe」

## 1. 在DrJava中创建程序

现在你已经为你的第一个Java程序做好了准备，你将在一个叫DrJava的程序中开发你的Java程序。DrJava包含了语法高亮、匹配括号、自动缩进和显示行号等特性。

1. 在上一节中的安装包已经在桌面上创建了DrJava的快捷方式『译者注：如果不慎删掉，还可以在如下目录中找到该程序：C:\Users\Username\algs4』。双击以启动DrJava，如果你收到一个Windows安装警告，点击「允许运行」或者「不禁止」

2. 在DrJava的主窗体中，请向下面一样准确无误得输入[HelloWorld.java](http://introcs.cs.princeton.edu/java/11hello/HelloWorld.java.html)中的代码，哪怕你只是漏掉了一个分号，这个程序也不会运行
{% highlight java %}
public class HelloWorld {
    public static void main(String[] args) { 
        System.out.println("Hello, World");
    }
}
{% endhighlight %}

在你输入的时候，DrJava会为你准备缩进

3. 最后，点击「保存」按钮来保存该文件，使用DrJava创建文件夹C:\Users\username\algs4\hello并将文件命名为「HelloWorld.java」，这个文件名是大小写敏感的而且必须匹配Java程序中的类名，其中username是你的Windows用户名

## 2. 在DrJava中编译程序