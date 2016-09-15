---
title: 在visual studio中调试网站
layout: post
guid: 2ef3550f-8cf3-400b-a55b-c512c9af8a1e
tags:
  - inBeisen
  - visual studio

---

这是在北森实习学到的东西的一个记录，主要分享一些我以前自学没有学到的小技巧或者有用的工具和知识

当新建了一个web站点（这里以ASP.NET MVC站点为例）之后，自然而然就会设计到如何调试的问题，通常有两种方式，对新手来说可能只有一种，那就是直接在VS的调试菜单中点击「从Google Chrome启动」，这里还可以选择不同的浏览器启动，但是道理都一样，反正就是调用VS自带的一个IIS Express部署网站然后调试

![从Google Chrome启动]({{ site.baseurl }}/media/files/2016/08/从Google Chrome启动.png)

网站启动之后可以看到右下角出现了一个浅蓝色的IIS Express图标

这种方式显然是大家都会的，再介绍一种新手可能不知道的方法

网站完成之后肯定都是会部署到线上供大家访问的，那究竟是用什么部署的呢？答案是IIS

IIS和IIS Express是两个不同但有紧密相连的东西，IIS全称Internet Information Services，是微软提供的一个互联网基本服务，说白了现在大家想在Windows Server上host基于ASP.NET的网站，基本都选IIS

IIS与Windows版本绑定，对应关系表参见 [Internet Information Services](https://zh.wikipedia.org/wiki/%E7%B6%B2%E9%9A%9B%E7%B6%B2%E8%B7%AF%E8%B3%87%E8%A8%8A%E6%9C%8D%E5%8B%99)，这里可以看出，每个Windows版本升级时会顺带升级IIS，而且IIS没有提供单独下载，同一版本的Windows，一般也只有高级别的版本可以使用IIS，比如Windows7 Home Basic就没有。与此对应的是IIS Express提供了单独下载，而且在安装VS的时候也会顺带安装一个IIS Express

话说回来，另一种调试方法就是在IIS里调试，下面主要分为将网站部署到IIS和在IIS中调试两部分

### 1. 将网站部署到IIS

 1. 首先在Windows功能中打开IIS，这个教程很多，略

 2. 打开IIS，添加网站

 ![IIS新建网站]({{ site.baseurl }}/media/files/2016/08/IIS新建网站.PNG)

 3. 配置信息如下，其中，网站名称随便填，物理路径要选择网站所有位置，主机名选择一个域名，反正都是host在本地，所以只要填一个合法的域名然后用SwitchHost把这个域名指向127.0.0.1即可

 ![IIS新建网站-配置]({{ site.baseurl }}/media/files/2016/08/IIS添加网站2.png)

 4. 注意，这里有两个我忽略的点，一个是修改host，将上面填写的域名指向本机，这个用SwitchHost可以很容易做到，另一个是身份验证，如果你访问了域名——比如我这里是viper.shuxiao.wang——发现只加载了html，没有加载js、css，而且httpcode是401的话，你多半是遇到了身份验证问题，这个问题我将在「网站host到IIS无法访问js和css」中讲，这是三种情况中的一种

 5. 如果顺利的话，这里应该可以访问到网站了，部署到IIS完成

 ![homepage]({{ site.baseurl }}/media/files/2016/08/homepage.png) 

### 2. 在VS中调试部署到IIS的网站

1. 思路：将VS的代码附加到chrome进程中，这样在chrome中访问网站时可以直接调用到VS中的代码

2. 附加进程：VS -> DEBUG -> Attach to Process 

 ![attach]({{ site.baseurl }}/media/files/2016/08/attach.PNG) 

3. 附加到进程，如下图

 ![process]({{ site.baseurl }}/media/files/2016/08/process.png) 

4. 附加到进程成功后如图，VS进入调试模式。如果左边端点不是实心红点而是空心红点，说明网站版本和VS版本不一样，在VS里面重新编译一次工程，然后刷新页面重新附加即可

 ![vs]({{ site.baseurl }}/media/files/2016/08/vs.png) 


 5. 附加成功后就可以开始调试了，比如上图中，我把断点打在HomeController的About方法下，所以我访问http://viper.shuxiao.wang/Home/About，VS中的断点就会直接命中，后面的调试就都一样了

  ![iis调试]({{ site.baseurl }}/media/files/2016/08/iis调试.png) 
