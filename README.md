# bnusss

## 索引
1. [关注主题](#topics)
2. [基本理论与方法](#theories_methods)
3. [成员介绍](#members)

## 关注主题

### 网络的空间嵌入
![Attentionnetworkexampleindiana.png](http://wiki.swarma.net/images/8/85/Attentionnetworkexampleindiana.png)

复杂网络是一种抽象建模复杂系统的强有力方法，它将任何一个系统简化成了节点和连线。然而，当网络的规模（通常是指节点的个数）大到一定程度以后，我们就无法用直观的方式来了解这个网络，取而代之的是计算一些网络的指标。所以，将网络嵌入到一个可视化的空间中，也就是给每个节点赋予一个坐标。近年来，人们发现了不少将网络可视化的方法，它不但可以让我们可以清晰地看出整个网络的形态，而且还提供了很多好处，例如：

- 如果我们选择的空间合适，那么空间的临近性就能够反映网络本身的临近性，这样一些网络上的动力学过程（例如信息的传播）就可以在新的空间下获得很好地表达，例如传播的动力学过程就展示为一种空间中的扩散过程。
- 每个节点的坐标可以看作是节点的抽象特征，因此被嵌入的空间就是整个网络每个节点的特征空间。也就是说，我们可以用一组向量来编码网络中的联系。于是，我们可以将这些特征向量辆输入进神经网络之中以完成分类或者预测。

近年来，随着[深度学习](http://wiki.swarma.net/index.php/%E6%B7%B1%E5%BA%A6%E5%AD%A6%E4%B9%A0)技术的火爆发展，使得发现事物隐含的特征特别重要，深度学习在某种程度上来说也是一种表征或者特征学习。因此，寻找每个节点的向量表示就是一种特征学习。近年来出现了几种常用的方法。本组关注如下几种方法：

#### DeepWalk

[DeepWalk](http://wiki.swarma.net/index.php/DeepWalk)是从Word2Vec技术中发展出来的一种方法。其中Word2Vec是一种神经网络算法，常常被用于自然语言处理，它的作用是根据上下文计算出每个单词的特征向量。而这个特征向量的寻找完全是根据神经网络训练而成的。

DeepWalk算法则是通过在网络上赋予一个随机游走的动力学，从而将这种随机游走转化成了一个节点的序列。那么，我们可以将节点比拟为单词，将序列比拟为句子，于是便可以训练Word2Vec模型，从而计算得到每个节点的嵌入坐标。

#### 根据流距离嵌入

[流网络](http://wiki.swarma.net/index.php/%E6%B5%81%E7%BD%91%E7%BB%9C)是本组长期关注的问题。流距离则是一种度量流网络之中任意两个节点之间距离的一种指标。那么，我们可以根据这个流距离将所有的节点嵌入到一个空间中。它的原理是，我要让每一对节点之间的欧氏距离能够尽可能地等于这对节点之间的流距离。

详情请见流距离的嵌入算法

#### 两种算法的比较

有趣的是，两种算法得到的嵌入结果非常的相似。具体详情请见[Word2Vec与流网络](http://wiki.swarma.net/index.php/Word2Vec%E4%B8%8E%E6%B5%81%E7%BD%91%E7%BB%9C)

#### 嵌入到双曲空间

在很多复杂网络或者复杂系统中，层级性都是一个极其重要的概念。因此，我们在考虑将网络嵌入到空间的时候，我们也可以将网络的层级性考虑进去，这就要将双曲空间的概念引进来。具体地，一个双曲空间中的极径方向可以表示层级，而极角则可以表示相似度。


### 复杂网络的深度学习

![Internet.gif](http://wiki.swarma.net/images/5/58/Internet.gif)

目前，随着大数据的积累使得深度学习技术有了非常重大的突破。而这种机器学习技术主要面对图像这种空间信息以及类似于人类语言的时间序列信息。

另一方面，复杂网络是各式各样的复杂系统的一种有力的抽象。而网络这种数据明显区分于图像和时间序列，却又介于图像和时间序列之间。当我们用临接矩阵表示网络的时候，它就可以被看作一种二维的图像；当我们用网络上的随机游走序列描述网络的时候，它就可以被看作一种时间序列数据。而无论是图像还是时间序列，都无法对网络进行简洁而准确的描述。

因此，我们考虑的课题是，既然深度学习在图像和时间序列数据上获得了如此重大的突破，为什么不能将这种技术应用到复杂网络上呢？但是，我们知道的一个难点就是：我们无法套用现成的深度学习算法来对网络进行学习，故而我们必须开发新的学习算法，以将深度学习技术应用到复杂网络上。


#### 进展

详见[复杂网络分类器](http://wiki.swarma.net/index.php/%E5%A4%8D%E6%9D%82%E7%BD%91%E7%BB%9C%E5%88%86%E7%B1%BB%E5%99%A8)


#### 前沿问题

复杂网络的分类是一种比较简单、直观、实用性强的问题。如果我们将复杂网络看作是各种复杂系统的表示，那么我们可以用大量的数据训练深度网络，以便得到对不同网络的分类器。从而通过网络作为代理手段，我们便能对不同的复杂系统做分类。

#### 参考文献

- Niepert M, Ahmed M, Kutzkov K. Learning Convolutional Neural Networks for Graphs[J]. 2016.


### 国际贸易流网络

![Tradenetworkvegetable](http://wiki.swarma.net/images/4/43/Tradenetworkvegetable.PNG)

如今的世界已经由于信息技术的发展形成了一个紧密连接的地球村，而国际贸易网络为地球村的形成提供了巨大的推波助澜的作用。联合国、世界经合组织等机构长期以来收集了大量高质量、详细的国籍贸易数据，这使得我们在这些数据的基础上研究国籍贸易流的分配形态及其演化成为了可能。

本研究组从2012年以来就开始利用这组数据集研究国籍贸易网络流。因此积累了一定的经验。

联合国的Comtrade数据集记录了从1960年到现在所有年份的国际贸易数据，甚至包括每一种细分产品的数据。这就使得我们不仅能够研究整个贸易网络，而且可以研究细分的产品市场的情况。有关这套数据集的介绍，请参看[国际贸易网](http://wiki.swarma.net/index.php/%E5%9B%BD%E9%99%85%E8%B4%B8%E6%98%93%E7%BD%91)

#### 产品多样性

如果我们将国家出口产品看作一种国家这个经济行为主体的一种投资，那么一个有趣的问题就是国家将如何有效地分配他们的投资资源，从而决定应该出口什么样的产品。以及，随着国家尺度的增长，它们出口的产品的多样性会发生怎样的变化。

对于第一个问题，我们发现运用最大化熵框架，可以给世界各国的贸易出口行为提供一个简洁而统一的解释；而对于第二个问题，我们发现了一种普适的国家GDP与出口产品多样性之间的S形曲线。

#### 参考文献

- Hongmei Lei,Ying Chen,Ruiqi Li, Deli He, Jiang Zhang: [Maximum Entropy for the International Division of Labor](http://www.swarma.org/thesis/download.asp?address=doc/jake_377.pdf&type=1&id=378); PLoS ONE 2015, 10(7): e0129955
- Hongmei Lei,Jiang Zhang: [Capabilities’ substitutability and the “S” curve of export diversity](http://www.swarma.org/thesis/download.asp?address=doc/jake_372.pdf&type=1&id=373); EPL 105 (2014) 68003
- Lunchao Hu,Kailan Tian,Xin Wang, Jiang Zhang: [The "S" curve relationship between export diversity and economic size of countries](http://www.swarma.org/thesis/download.asp?address=doc/jakeScurve.pdf&type=1&id=363); Physica A 391 (2012) 731–739

#### 网络的层级性

我们可以分产品研究它们的贸易网络特征。我们发现，网络的层级性实际上是与这种产品的生产工艺复杂度正相关的。具体的研究可以参看：

Peiteng Shi,Jiang Zhang,Bo Yang, Jingfei Luo: [Hierarchicality of Trade Flow Networks Reveals Complexity of Products](http://www.swarma.org/thesis/download.asp?address=doc/jake_374.pdf&type=1&id=375); PLoS ONE 2014, 9(6): e98247

#### 国际贸易网络的演化

运用流网络的技术研究国际贸易网的演化将能够得到很多有意思的结果。包括各个国家的发展轨迹，整个世界经济贸易生态系统等。


### 投入产出流网络

投入产出网是描述了一个国家内部产业与产业之间经济与技术联系的网络，节点是产业，连边是产业间的实物流，或者现金流，反映的是产业与产业间中间投入的关系。而投入产出网天生就可以转化为一个开放流动网络，并且其源、汇都有现实的经济意义代表增加值和最终消费。

在OECD的数据官方网站上有各国每年的投入产出数据，所有产业被分为34个大类。利用该数据，构建出国家的投入产出流网络后，我们主要关心以下几个问题：

- 流距离与流量之间是否存在某种关系：实验结果证明流距离比流量所包含的信息更多，主要是流距离还包含了投入产出网的一些拓扑性质。
- 如果体现国家投入产出网的结构：我们依托两类特征距离，从源距离和到汇距离刻画了不同国家的投入产出网的结构，我们发现中美两国投入产出结构有共同之处也有不同之处，并给与了相应的解释。
- 如何刻画某国某产业的演化规律：我们以中国房地产为例，探讨了产业随时间的演化，并给与了相应的现实事件做对应，发现我们的方法在一定程度上符合体现产业演化的规律。

具体结果及方法请参考[投入产出流网络](http://wiki.swarma.net/index.php/%E6%8A%95%E5%85%A5%E4%BA%A7%E5%87%BA%E6%B5%81%E7%BD%91%E7%BB%9C)


### 集体注意力流

随着人类进入信息时代，数据和信息的进一步泛滥反而促使了人类的注意力成为了一种稀缺。注意力经济则是将注意力作为一种稀缺资源，研究它的分配和交换。然而，我们关注更多的则是从人机关系的视角来看，注意力资源起到了一种什么样的作用？答案是，注意力可以比拟为一种“能量流”，而计算机程序（网站、APP、应用等）则可以看作是竞争能量流的物种。有关这一观点的详细讨论，请参看[集智俱乐部](http://wiki.swarma.net/index.php/%E9%9B%86%E6%99%BA%E4%BF%B1%E4%B9%90%E9%83%A8)的新书[走近2050](http://wiki.swarma.net/index.php/%E8%B5%B0%E8%BF%912050)。

![S28786557.jpg](http://wiki.swarma.net/images/f/fa/S28786557.jpg)

而另一方面，我们每个人在互联网上的行为都已经被社交媒体大数据所记录，这就使得我们可以获得有关人类群体的注意力及其流动的数据。历史上，惠普实验室的Huberman研究组早在2009年就提出了Collective attention一词来描述互联网上大规模群体的注意力分配，并主张运用大数据方法来定量研究。

进一步，本研究组早在2013年就开始运用我们独创的[开放流网络](http://wiki.swarma.net/index.php/%E5%BC%80%E6%94%BE%E6%B5%81%E7%BD%91%E7%BB%9C)的方法研究集体注意力的流动。

更多详情请参看[集体注意力](http://wiki.swarma.net/index.php/%E9%9B%86%E4%BD%93%E6%B3%A8%E6%84%8F%E5%8A%9B)词条。

#### 前沿问题
- 概念空间与集体注意力：无论是知识图谱还是概念地图，它们都更关注知识之间的连接。而结合考虑了人类集体注意力之后，概念空间将变为一种动态的网络，其中集体注意力流动不仅会沿着概念地图流动，更可能塑造概念网络。注意力与概念网络之间的关系可以类比为水流和河道之间的关系。
- 注意力流动与自然语言处理：由于人类的注意力在每一个时刻只能关注一个事物对象，因此，注意力在时间中的流动就构成了一个序列。与此类似，人类的语言也是一种符号的序列。因此，注意力流动与语言之间存在着深层次的联系。于是，可以将自然语言处理技术应用到集体注意力的研究之中。初步进展包括将流网络中的流距离与深度学习中的Word2Vec技术作对比，参看Word2Vec与流网络
- 运用注意力流网络预测社区发展：注意力流网络可以从宏观和联系的层面看到用户流量在系统各个部分之间的分配和转移。因此，如何运用机器学习的方法，运用注意力流网络来预测一个社区或网站的未来发展成为了一非常有意义的问题。
- 注意力流网络的演化：河道可以引导水流的流动，水流反过来可以冲刷河道。我们关注集体注意力是如何沿着注意力网络演化和发展的，以及如何塑造注意力网络的。进一步，我们将尝试通过当前时刻注意力网络的状态预测未来网络的发展，例如什么网站将可能成为黑马，变得越来越重要？
社会化推荐与注意力网络之间的关系：当前的移动互联网和社会媒体已经改变了人们的阅读习惯，因此注意力转移将会受到社会化推荐的重要影响。从模型的角度研究社会化推荐与注意力网络之间的关系将是一个重要的理论问题。

#### 主要参考资料

- 集智俱乐部，[走近2050——注意力、互联网与人工智能](http://wiki.swarma.net/index.php/%E8%B5%B0%E8%BF%912050)，人民邮电出版社，2016
- 集智WIKI词条：[集体注意力](http://wiki.swarma.net/index.php/%E9%9B%86%E4%BD%93%E6%B3%A8%E6%84%8F%E5%8A%9B)
- Peiteng Shi,Xiaohan Huang,Jun Wang, Jiang Zhang: [A Geometric Representation of Collective Attention Flows](http://www.swarma.org/thesis/download.asp?address=doc/jake_380.pdf&type=1&id=381); PLoS ONE 10(9): e0136243, 2015
- Lingfei Wu,Jiang Zhang,Min Zhao: The Metabolism and Growth of Web Forums; PLoS ONE 2014, 9(8): e102646


### 城市的形态与生长


![Matchinggrowthspatialattractionlondon](http://wiki.swarma.net/images/8/88/Matchinggrowthspatialattractionlondon.png)

2014年，人类已经有一半的人口居住到了城市，而城市化的进程将进一步快速增长。据称，到了2050年，人类的城市化率将会达到70%。因此，研究城市的形态、生长与演化具有十分重要的意义。

本研究组关注的一个研究课题就是城市的建模以及利用大数据分析的方法研究城市。

#### 城市生长模型

复杂性研究的一个巨大魅力就在于纷繁复杂的现象背后可能存在着极其简单的规则。对于城市这样复杂的系统来说，近年来的复杂性研究已经揭示出了包括Zipf律、Gibrat定律，[异速生长律](http://wiki.swarma.net/index.php/%E5%BC%82%E9%80%9F%E7%94%9F%E9%95%BF%E5%BE%8B)等定量化的、普适性极强的规律。甚至，人们也提出了各式各样的可以解释城市形态和生长的定量模型。

本研究组基于前人的研究提出了自己的城市生长模型。该模型基于一个非常简单的假设：即人类进入城市定居后，需要相互连通在一起，从而使得人们可以便利地共享各种资源。除此之外，我们可以为城市道路，以及人们彼此之间的社会经济交互制定简单的规则，就可以创造出一个模型化的城市生长模型。该模型不仅可以解释长期以来人们观察到的各种异速生长律，还能够定量化地给出人口、道路、GDP在空间分布的形态，并与实证数据高度吻合。有关，这一模型的详细内容，请参看：[匹配生长随机几何图模型](http://wiki.swarma.net/index.php/%E5%BC%82%E9%80%9F%E7%94%9F%E9%95%BF%E5%BE%8B)。

#### 参考文献

- 集智WIKI词条：[匹配生长随机几何图模型](http://wiki.swarma.net/index.php/%E5%8C%B9%E9%85%8D%E7%94%9F%E9%95%BF%E9%9A%8F%E6%9C%BA%E5%87%A0%E4%BD%95%E5%9B%BE%E6%A8%A1%E5%9E%8B)
- Jiang Zhang,Xintong Li,Xinran Wang, Wen-xu Wang, Lingfei Wu: [Scaling behaviours in the growth of networked systems and their geometric origins](http://www.swarma.org/thesis/download.asp?address=doc/jake_379.pdf&type=1&id=380); SCIENTIFIC REPORTS 2015, 5: 9767
- Xintong Li,Xinran Wang,Jiang Zhang, Lingfei Wu: [Allometric scaling, size distribution and pattern formation of natural cities](http://www.swarma.org/thesis/download.asp?address=doc/jake_376.pdf&type=1&id=377); Palgrave Communications, 1, 15017 (2015)


#### 基于大数据的城市研究

目前，基于大数据的方法研究城市问题也是目前科学界的一个主流研究方法。

本研究组做过的一个研究就是利用手机数据来度量人类的移动，并推测出路网的疏运效率，具体内容参见文章：

Lei Dong, Ruiqi Li,Jiang Zhang, Zengru Di: [Population-weighted efficiency in transportation networks](http://www.swarma.org/thesis/download.asp?address=doc/jake_381.pdf&type=1&id=382); Scientific Reports, 6: 26377

#### 前沿问题

- 城市生长模型的进一步探讨：目前匹配生长随机几何图模型已经在城市建模等方面取得了一定的进展，该模型可以给出城市的异速生长律、人口、交通路网、GDP等变量的空间分配情况。
- 人类移动与自然语言处理：从本质上讲，人类的移动行为和自然语言具有一定的相似性：它们都是一个抽象的符号序列。因此，将自然语言处理中的技术应用到人类移动行为上将会有比较有意思的结果。


### 参考链接
- [Jake研究小组关注课题](http://wiki.swarma.net/index.php/Jake%E7%A0%94%E7%A9%B6%E5%B0%8F%E7%BB%84%E5%85%B3%E6%B3%A8%E8%AF%BE%E9%A2%98)


## 基本理论与方法
### 开放流网络

![Exampleflownetwork](http://wiki.swarma.net/images/4/4c/Exampleflownetwork.PNG)
所谓的开放流网络，是一种加权有向网，并且具有源和汇以表示环境。这种网络是一种建模自然、社会中的开放流系统的一个有力理论工具，并且多年的积累使得我们形成了一套独特的研究方法论。如上图所示就是一个示意的流网络。

有关这种网络的进一步说明，请参看[流网络](http://wiki.swarma.net/index.php/%E6%B5%81%E7%BD%91%E7%BB%9C)

#### 流网络的普适规律

通过分析积累的大量的流网络数据，我们找到了属于流网络的普适性规律，包括[流网络的异速标度律](http://wiki.swarma.net/index.php/%E6%B5%81%E7%BD%91%E7%BB%9C%E7%9A%84%E5%BC%82%E9%80%9F%E6%A0%87%E5%BA%A6%E5%BE%8B)、流网络的异速生长律、流网络的耗散律、[流网络的引力定律](http://wiki.swarma.net/index.php/%E6%B5%81%E7%BD%91%E7%BB%9C%E7%9A%84%E5%BC%95%E5%8A%9B%E5%AE%9A%E5%BE%8B)等，以及包括流量的无标度分布。更多详细内容请参看流网络词条

##### 参考文献

J.Zhang, Y.J. Feng: ['Common Patterns of Energy Flow and Biomass Distribution on Weighted Food Webs'](http://arxiv.org/abs/1208.1560). Physica A 405 (2014) 278–288

#### 流距离与网络嵌入

利用马尔可夫链的性质，我们可以定义流网络上任意两点的平均流距离。这样就可以为整个网络赋予一种几何结构。进一步，我们可以将整个网络嵌入到一个欧氏空间中，就可以为每一个节点赋予一个向量。这样，我们便可以直观而清晰地看到每个节点的重要性程度以及它们的聚类。

具体的流距离概念，请参看[流距离](http://wiki.swarma.net/index.php/%E6%B5%81%E8%B7%9D%E7%A6%BB)，以及根据流距离的流网络嵌入

##### 参考文献

- Liangzhu Guo,Xiaodan Lou,Peiteng Shi, Jun Wang, Xiaohan Huang, Jiang Zhang: [Open Flow Distances on Open Flow Networks](http://www.swarma.org/thesis/download.asp?address=doc/jake_378.pdf&type=1&id=379); Physica A, Vol 437, 1, 235–248
- Peiteng Shi,Xiaohan Huang,Jun Wang, Jiang Zhang: [A Geometric Representation of Collective Attention Flows](http://www.swarma.org/thesis/download.asp?address=doc/jake_380.pdf&type=1&id=381); PLoS ONE 10(9): e0136243, 2015


### 异速生长律

![Life-pulse.gif](http://wiki.swarma.net/images/2/29/Life-pulse.gif)

异速生长律（也叫异速标度律，Allometric scaling）是很多复杂系统，包括生命、城市、国家都具备的一种规律，它刻画的是系统的宏观变量（如新陈代谢）随着系统规模（如生物体体重）生长而幂律生长的关系。有关异俗生长的详细表述，请参看异速生长律

早期的异速生长起源于生物学。后来人们发现这套规律也适用于城市、网站等其它复杂系统。本研究组在异速生长方面的研究已经有很长时间的历史。其中，主要分为了宏观系统的异速生长，以及网络，特别是流网络的异速生长这两部分。

#### 宏观系统的异速生长

我们将宏观系统视为一个整体，研究系统两个宏观变量之间的幂律关系。主要从实证数据中找到这些幂律关系，并对幂律的指数进行系统化的分类研究。

例如，我们曾研究过国家的异速生长律，发现很多宏观变量都与国家的GDP呈现稳定的幂律关系。

- Jiang Zhang,Tongkui Yu: [Allometric Scaling of Countries](http://www.swarma.org/thesis/download.asp?address=doc/jake_337.pdf&type=1&id=338); Physica A Vol.389(2): 4887-4896(2010)

再比如说，对于网络社区，用户总产出的活动事件就与用户数呈现超线性的幂律关系。

- Ling-Fei Wu,Jiang Zhang: [Accelerating growth and size-dependent distribution of human online activities](http://www.swarma.org/thesis/download.asp?address=doc/jake_361.pdf&type=1&id=362); Physical Review E 84, 026113, 2011


#### 网络的异速生长
另外一类研究就是针对某一个或者某一类网络进行异速生长的研究。比如，我们花费了很大的精力研究流网络的异速生长律问题，包括异俗标度律和异速生长律。

- Jiang Zhang,Liangpeng Guo: [Scaling Behaviors of Weighted Food Webs as Energy Transportation Networks](http://www.swarma.org/thesis/download.asp?address=doc/jake_285.pdf&type=1&id=337); Journal of Theoretical Biology 264 (2010) 760–770
- Jiang Zhang,Lingfei Wu: [Allometry and Dissipation of Ecological Flow Networks](http://www.swarma.org/thesis/download.asp?address=doc/jake_371.pdf&type=1&id=372); PLoS ONE 2013, 8(9): e72525.


## 成员介绍
* [Jake](http://wiki.swarma.net/index.php/Jake)
