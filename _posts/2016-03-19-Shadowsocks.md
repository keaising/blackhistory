---
title: ShadowSocks 使用教程
layout: post
guid: 2ef3550f-8cf3-400b-a55b-c512c9af8a2c
tags:
  - Tutorial

---

### 1  iOS Surge

复制下面这个链接

http://shuxiao.wang/surge.config

打开Surge，Zuo上角 Edit ，Download Configuration from URL， 粘贴进去，Done！

#### 2 iOS Shadowrocket

6块钱购买Shadowrocket或者去Twitter[@ShadowRocketApp](https://twitter.com/shadowrocketapp)参与[TestFlight](https://docs.google.com/forms/d/115OwGBkww8-pUmW4xcH00c1103_wtLCfUBZjhzVqEqY/viewform)内测，需要填写你的AppleID和TwitterID，我更建议购买，TestFlight计划随时可能结束而且每个Build只有60天使用时间

点击右上角「+」添加一个配置文件，填写内容如下，密码问我要

![ShadowRocketConfig]({{ site.baseurl }}/media/files/2016/03/ShadowRocketConfig.png)

然后退回主界面，点击「Setting」 -> 「Config」，在「Remote Files」里面填写 http://shuxiao.wang/surge.config 

退回主界面，点击Not Conneted右边那个按钮，会提示是否允许建立VPN之类的，点击允许，就可以开始使用了

我一般是将ShadowsockRocket的插件添加到通知栏中，这样可以比较方便得打开和关闭，同时可以看到即时流速

![ShadowRocketNotice]({{ site.baseurl }}/media/files/2016/03/ShadowRocketNotice.png)


#### 3  Windows 7/8/8.1/10

请按照自己的需求下载Windows客户端：

+ Windows 7 - IPv4 翻墙：[Windows7.IPv4]({{ site.baseurl }}/software/Windows7.IPv4.rar)

+ Windows 7 - IPv6 免流量/翻墙：[Windows7.IPv6]({{ site.baseurl }}/software/Windows7.IPv6.rar)

+ Windows 8、8.1、10 - IPv4 翻墙：[Windows10.IPv4]({{ site.baseurl }}/software/Windows10.IPv4.rar)

+ Windows 8、8.1、10 - IPv6 免流量/翻墙：[Windows7.IPv4]({{ site.baseurl }}/software/Windows10.IPv6.rar)

解压缩到一个喜欢的地方，双击Shadowsocks.exe，就可以开始使用了

如果你只有IPv4环境的话（比如校内无线上网、家里宽带、校外上网），选择IPv4版本，此时只能翻墙。确认自己有IPv6环境（比如校内用有线上网），可以使用IPv6版本免流量且翻墙。

需要注意的一点是Windows7版本需要.Net3.5，Windows7系统应该是内置了所以没有问题，Windows8、8.1、10的用户尽量下载Windows10版本，避免遇到安装.Net3.5的问题。

同一系统版本的IPv4和IPv6版本其实完全一致，只是默认设置有一点区别，需要切换的时候右键任务栏小飞机 -> 服务器，选择IPv4或者IPv6即可。


### 4 Android

只测试了原生Android和魅族的Flyme5.0以上系统，其他机型请仿照

先下载[Android版Shadowsocks]({{ site.baseurl }}/software/shadowsocks.apk)到手机上，安装，需要什么权限就给什么权限，安装好之后配置如图：

![AndroidSetting]({{ site.baseurl }}/media/files/2016/03/AndroidSetting.png)

配置好之后，点击右上角小飞机或者云朵就可以开始使用了

<--

#### 2.2  Windows 10

先打开Shadowsocks.exe，再打开网络和共享中心，如下图，点击有线网络的「以太网」

![网络和共享中心]({{ site.baseurl }}/media/files/2016/03/1.png)

弹出以太网状态界面，点击「属性」，如下图

![以太网 属性]({{ site.baseurl }}/media/files/2016/03/2.png)

弹出详细的以太网属性界面，这里重头戏来了

![以太网 属性]({{ site.baseurl }}/media/files/2016/03/3.png) 

按理说，如果你是在交大上网的话，我圈出的IPV4和IPV6都应该是选中的状态（Checked - 打了勾的）

此时，如果你要使用IPV6免流量通道，就去掉IPV4的勾，然后点击确定和保存退出设置就可以上网了，即使右下角的网络图标有个黄色的感叹号也不影响你上网

但是，如果是已经使用了IPV6免流量，需要回到学校内部网络访问学校资源（比如图书馆、MIS系统和PT），这时你要做两件事：1. 选中IPV4的勾，确认保存； 2. 右下角右键关闭Shadowsocks

教程比较简单，有其他问题请直接咨询我 (*^__^*)

 -->

### 0. 结语

（这部分不用看，不影响使用

在VPS上搭建Shadowsocks翻墙和走IPV6免流量通道的教程如下：[秋水逸冰 - Shadowsocks Python版一键安装脚本](https://teddysun.com/342.html)

需要注意的是可能需要在CentOS上开放防火墙，我的做法是直接关闭了我的防火墙，其实只需要打开Shadowsocks占用的那个端口即可，但是关闭命令更简单嘛，而且我的VPS也仅仅这一个用途所以无所谓了
