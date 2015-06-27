---
title: 不确定性数据和异构数据
layout: post
guid: 2ef3550f-8cf3-400b-a55b-c512c9af8a2m
categories: BigData

---


老师给的方向：在大数据研究中，当数据中有不确定性、错误或者遗失，如何进行特征提取。

这句话至少有三个需要探讨的地方：

1. 研究的数据是什么样的数据，有哪些类型，数据有多大？
2. 什么是数据的不确定性；什么是错误，错误从何而来，又能错误到什么程度；数据为何遗失，如何补全或者应对？
3. 特征提取，现有什么特征提取方法，现有方法是如何应对第二个问题的，如何改进以适应铁路数据？

第一个问题暂时没有能力回答，因为，我没有能拿来直接用的数据Orz...

第二个问题能回答一部分，以下是找到的答案：

####不确定性数据（uncertain data）

不确定性数据的产生原因比较复杂，可能是原始数据本身不准确或是采用了粗粒度的数据集合，也可能是为了满足特殊应用目的或是在处理缺失值、数据集成过程中而产生的。详细原因可以划分如下：

1. 原始数据不准确。这是产生不确定性数据最直接的因素。首先，物理仪器所采集的数据的准确度受仪器的精度制约。其次，在网络传输过程（特别是无线网络传输）中，数据的准确性受到带宽、传输延时、能量等因素影响。最后，在传感器网络应用与RFID应用等中，周围环境也会影响原始数据的准确度。
2. 使用粗粒度数据集合。很明显，从粗粒度数据集合转换到细粒度数据集合的过程会引入不确定性。例如，假设某人口分布数据库以乡为基础单位记录全国的人口数量，而某应用却要求查询以村为基础单位的人口数量，查询结果就存在不确定性。
3. 满足特殊应用目的。出于隐私保护等特殊目的，某些应用无法获取原始的精确数据，而仅能够得到变换之后的不精确数据。
4. 处理缺失值。缺失值产生的原因很多，装备故障、无法获取信息、与其他字段不一致、历史原因等都可能产生缺失值。一种典型的处理方法是插值，插值之后的数据可看作服从特定概率分布。另外，也可以删除所有含缺失值的记录，但这个操作也从侧面变动了原始数据的分布特征。
5. 数据集成。不同数据源的数据信息可能存在不一致，在数据集成过程中就会引入不确定性。例如，Web中含很多信息，但是由于页面更新等因素，许多页面的内容并不一致。

以上内容来自论文：[*周傲英,金澈清,王国仁等.不确定性数据管理技术研究综述[J].计算机学报,2009,32(1):1-16.DOI:10.3724/SP.J.1016.2009.00001*](http://d.g.wanfangdata.com.cn/Periodical_jsjxb200901001.aspx)

该论文后面还有一些有价值的论述，待我看完再细说。

在一家调查公司的文章[*大数据如何解放了调研工作*](http://www.millwardbrown.com/docs/default-source/china-downloads/newsletter/1-millward_brown_pov_how_big_data_liberates_research-cn.pdf?sfvrsn=2)中提到：大数据的一个显著特征是他们通常是原始格式的非结构化或者半结构化数据，且具有不确定性，一种名为“实体分析”的数据管理方法有助于管理大数据噪声。

不过在看了百度百科关于实体分析的词条后感觉这东西跟我要的好像不太相关。

另外，[*也有人指出*](http://www.boaoreview.org/html/boaoyazhouluntan2015nianhui/boaoyazhouluntanz/2015/0321/3463.html)：

>大数据的不确定性表现在高维、多变和强随机性等方面，不要以为有了大数据就可以增加确定性，不确定性会持续存在，而且因为大数据的存在，结果反而导致了更不确定性。

####异构数据（heterogeneous data）

异构数据来自计算机科学领域，至今没有在百科找到一个词条准确描述异构数据的定义，最接近的应该是[*异构数据库*](http://baike.baidu.com/view/78075.htm)一词，另外在[*Service Data Objects*](http://en.wikipedia.org/wiki/Service_Data_Objects)中提到了该技术可以对异构数据进行处理，很遗憾也没有定义何为异构数据。

维普中能找到多篇用XML对异构数据进行半结构化处理的硕士论文，其中也都没有对异构数据进行准确定义，不过用得比较多的一个说法是：异构数据是一个含义丰富的概念，不仅指不同数据库系统之间的数据是异构，如Oracle和SQL Server数据库，而且包括不同结构的数据之间的异构，如结构化的SQL Server数据库数据和半结构化的XML数据。

总的来说，这都是计算机科学用到概念。

从这个思路出发，如果将异构的概念泛化，对铁路或者交通数据来说可能是这些：

* 道路/铁路旁传感器的声音、图像、文本信息
* 指挥系统中传递的各种指令
* 道路维修系统的维修记录
* 事故处理部门的事故处理记录
* 诸如此类的各种数据

如果想将所有的这些数据全部都有效的加以利用，进行故障预测、风险评估，很可能需要进行结构化或者半结构化处理，处理之后还需要进行特征提取等步骤直到可以提供给分类器或者回归模型进行计算。

那么我们就回到了最初的那个问题：如何在异构数据和不确定性数据的基础上进行特征提取？

PS: 还有一个综述性的PPT可供参考：[*多源异构大数据的机器学习关键技术研究进展*](http://www.36dsj.com/archives/18603)