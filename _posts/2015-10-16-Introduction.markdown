---
title: 1. Introduction - Programming Windows 6th Edition
layout: post
guid: 2ef3550f-8cf3-400b-a55b-c512c9af8a2a
tag: 
  - Programming Windows
  - Translation

---

这本书——Windows程序设计第六版——是一本在Microsoft Windows 8操作系统下进行应用开发的技术指南。在写作这本书的时候（2012年8月1日），Windows 8尚未完成（当时还处于技术预览版阶段——译者注），这本书也没有完成。你现在阅读的是这本书的电子书预览版，该版本是基于2012年5月31日发布的Windows 8的客户预览版（Build 8400）写作的。

微软已经宣布，Windows 8会在2012年10月26日正式发布，微软出版社（Microsoft Press）和我计划在十一月中旬发布这本书的最终版本。

为了配合本书的使用，读者需要安装Windows 8客户预览版和Microsoft Visual Studio Express 2012 RC for Windows 8，二者都可以从Windows 8 开发者门户下载：[http://msdn.microsoft.com/windows/apps](http://msdn.microsoft.com/windows/apps)

如果需要安装Visual Studio，点击页面的「Download the tools and SDK」进入

### Windows 8 的版本

从很大程度上来说，Windows 8是用来运行跟Windows 7一样的应用程序的。当Windows 8在今晚晚些时候发布的时候，会有一个普通的Windows 8版本和一个功能更加丰富、面向技术爱好者和专业人士的Windows 8 Pro版本，不管是Windows 8还是Windows 8 Pro，都可以运行两种类型的应用程序：

+ 桌面应用
+ 全新的Windows 8应用

桌面应用就是当下正运行在Windows 7上的传统Windows程序，他们通过通过Windows应用程序接口（更令人熟知的名字是Win32 API）与系统进行交互，为了顺利运行这些桌面应用，Windows 8包含一个大家熟悉的Windows桌面。

而全新的Windows 8应用则代表了一种对传统Windows的突破。这些程序通常运行在全屏模式下——尽管两个程序可以通过一个叫「snap」的模式共享整个屏幕——而且这些程序大多都为触控和平板情景下的使用进行了专门的优化。这类程序只能通过微软官方运营的应用商店进行购买和下载安装。

Windows 8应用有着全新的设计风格，部分设计灵感来自城市环境，这个设计风格注重内容而非程序界面，特点在于使用质朴的字体、干净开放的样式、基于磁贴的界面和过渡动画。

除了运行在x86处理器上的Windows 8版本之外，还有一个运行在ARM处理器上的Windows 8版本，这个版本被称作Windows RT，将会被预装在低功耗的平板设备上。除了部分预装在系统中的桌面应用，Windows RT将只能运行全新的Windows 8应用。

许多开发者第一次接触到Windows 8设计规则是在Windows Phone 7上，Windows 8提现了微软公司对大大小小的计算机在未来如何进化的思考。几年过去了，微软试图将传统Windows桌面应用程序的设计应用到诸如手机和平板这类小尺寸的手持设备上，现在一个使用手机的用户界面设计已经被移植到平板和桌面上。

这个新环境的一个重要特点就是强调多点触控，多点触控显著地改变了人与电脑之间的关系。事实上，多点触控这个词已经在某种意义上过时了，因为现在所有的新触控设备都支持多个手指的触摸，所以更简单的「触摸」一词就足够形容现在的设备了。部分新的Windows 8应用的设计界面将触摸、鼠标和手写笔的输入视为统一的输入方式，因此该应用程序在三种输入设备中都可以很好得运行。

### 本书重点