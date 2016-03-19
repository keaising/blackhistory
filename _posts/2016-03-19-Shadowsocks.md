---
title: ShadowSocks 使用教程
layout: post
guid: 2ef3550f-8cf3-400b-a55b-c512c9af8a2c
tags:
  - Tutorial

---

### 引言

在VPS上搭建Shadowsocks翻墙和走IPV6免流量通道的教程如下：[秋水逸冰 - Shadowsocks Python版一键安装脚本](https://teddysun.com/342.html)

需要注意的是可能需要在CentOS上开放防火墙，我的做法是直接关闭了我的防火墙，其实只需要打开Shadowsocks占用的那个端口即可，但是关闭命令更简单嘛，而且我的VPS也仅仅这一个用途所以无所谓了

### IPV4 翻墙教程

#### iOS

复制下面这个链接 http://shuxiao.wang/surge.ios 打开Surge，右上角 Edit ，Download Configuration from URL， 粘贴进去，Done！

#### Windows 7/8/8.1/10

打开我给你的文件夹，双击Shadowsocks.exe，开始使用吧。这个软件资源占用较低，可以一直开着。

如果提示代理不可用，Windows 10用户可以尝试下面的设置，其他Windows版本我手上没有。。无法测试

开始 -> 设置 -> 网络和Internet -> 代理， 如图填写

1. 使用代理（勾选）

2. 地址： 127.0.0.1

3. 端口1080

### IPV6免流量通道

#### iOS

Surge不支持IPV6，想多了

#### Windows 10

先打开Shadowsocks.exe，再打开网络和共享中心，如下图，点击有线网络的「以太网」

![网络和共享中心]({{ site.baseurl }}/media/files/2016/03/1.png)

弹出以太网状态界面，点击「属性」，如下图

![以太网 属性]({{ site.baseurl }}/media/files/2016/03/2.png)

弹出详细的以太网属性界面，这里重头戏来了

![以太网 属性]({{ site.baseurl }}/media/files/2016/03/3.png)

按理说，如果你是在交大上网的话，我圈出的IPV4和IPV6都应该是选中的状态（Checked - 打了勾的）

此时，如果你要使用IPV6免流量通道，就去掉IPV4的勾，然后点击确定和保存退出设置就可以上网了，即使右下角的网络图标有个黄色的感叹号也不影响你上网

但是，如果是已经使用了IPV6免流量，需要回到学校内部网络访问学校资源（比如图书馆、MIS系统和PT），这时你要做两件事：1. 选中IPV4的勾，确认保存； 2. 右下角右键关闭Shadowsocks

教程比较简单，有其他问题请直接咨询我