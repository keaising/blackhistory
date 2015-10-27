---
title: MATLAB实现主成分分析的简要代码
layout: post
guid: 2ef3550f-8cf3-400b-a55b-c512c9af8a2n
tags:
  - Assignment
  - MATLAB

---


特征提取有很多方法，今天研究了主成分分析法，找了个实例，并根据实例自己用MATLAB实现了，流程大致为：

1. 对所需进行特征提取的向量X进行列处理，认为每一列是一个feature，求出每一列的均值(mean_X)和方差(sigma_X)
2. 根据第一步中的数据，对每一列进行方差归一化，得到归一化后的向量(normal_X)
3. 求出normal_X的协方差矩阵(sigma_normal_X)
4. 求出协方差矩阵的特征向量(T)和特征值(lamda)，从小到大排列
5. 计算每个特征值的方差贡献率和累积方差共享率，选择出方差贡献率最大的那几个特征，作为主要成分

代码如下：

{% highlight matlab linenos %}
% 设X为待分析的向量， 获取X的行列数
[Xrow,Xcol]=size(X);

for j=1:Xcol
    mean_col(j)=mean(X(:,j)); % 列均值
    sigma_col(j)=sqrt(cov(X(:,j))); %列方差
end

for i=1:Xrow
    for j=1:Xcol
        normal_X(i,j)=(X(i,j)-mean_col(j))/sigma_col(j); % 方差归一化
    end
end

sigma_normal_X=cov(normal_X); % 归一化后的向量的协方差矩阵

[T,lambda]=eig(sigma_normal_X); % 协方差矩阵的特征向量和特征值，从小到大排列

Xsum=sum(sum(lambda,2),1);
for i=1:n
    fai(i)=lambda(i,i)/Xsum; % 方差贡献率
end
for i=1:n
    psai(i)= sum(sum(lambda(1:i,1:i),2),1)/Xsum; % 累计方差贡献率
end

{% endhighlight matlab %}

* 代码参考：[主成分分析MATLAB源代码](http://www.matlabsky.com/thread-668-1-1.html)
* 数据来源：[主成分分析MATLAB源程序](http://wenku.baidu.com/view/795d39dca58da0116c17497d.html)
* 示例学习：[北大数学院主成分分析课件](http://www.math.pku.edu.cn/teachers/tli/Teaching/Multivariate/Slides/Slide0516.ppt)
* 详细解答：[主成分分析-最大方差解释](http://www.cnblogs.com/jerrylead/archive/2011/04/18/2020209.html)