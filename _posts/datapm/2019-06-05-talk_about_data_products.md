---
layout:     post
title:      "谈谈我对数据产品的理解"
subtitle:   "talk about data products"
date:       2019-06-05 19:16:32
author:     "soaringsoul"
header-img: "img/posts/default_post.jpg"
catalog: true
tags:
    - 学习笔记


---

## 1 数据产品与产品之间的关系

面向对象编程 (Object Oriented Programming，简称OOP) 语言中有个术语叫“继承”，子对象会继承父对象的属性。例如猫是动物的一种，它具有了动物的属性、波斯猫又是猫的一种，它又具有了猫的所有属性。![oop](/img/oop.jpg)

那么，从OOP术语来看，“数据产品”是数据相关的产品，是“产品”的子集。继承了“产品”的属性，它具有“产品”的所有属性，并在“产品”所有通用属性的基础上具备了一般产品所不具备的“数据”属性。

## 2 什么是产品

对于什么是产品这个问题，我认为这是一个开放性的问题，没有标准答案，各行各业对产品这一概念的定义都是有差异的，不同的产品经理对产品这一概念的理解应该也是见仁见智，或者有些产品经理压根没想过这个问题。


我刚刚从事产品经理这个职业时，对于什么是”产品”这一问题翻阅了一些书籍，一直想找到一个比较贴切的解释，不过绝大部分书籍都是默认读者已经知道是什么产品，对产品的概念并不涉及，只有苏杰在《人人都是产品经理》中的对产品进行了定义：

> 产品：解决某个问题的东西。
>
> ?															                   ——《人人都是产品经理》

后来，我无意中在维基百科上搜索`product`这一词条，看到了维基百科上对产品的定义，有种恍然大悟的感觉，原来苏先生也是参考维基百科的词条给产品下的定义。

> product is an item that serves as a solution to a specific consumer problem.
>
> ?                                                                                       —— wiki

翻译一下：

> 产品是一个用以解决某个具体用户问题的东西。

维基百科上对`product`这个词语的解释与定义，我认为非常的准确，翻译成中文反而不如英文贴切，苏先生在翻译时不知道是有意还是无意漏掉了特别关键的一个词语`consumer`。产品是用以解决特定用户的特定问题的，这也是为什么在进行产品规划与设计时要先明确用户和需求的本质。

这个定义里面有几个关键词：

* solution 解决方案
* specific 特定场景
* consumer 用户
* problem 问题



换句话说，在商业社会里，只要可以解决用户在某个特定场景下问题的东西，无论是服务还是实体物品都可以视作产品。

这样说来，我们在日常生活中接触到的衣食住行的方方面面其实都是产品，不管是有形的实物(如我们使用的手机、电脑，身上穿的衣服，鞋子)，还是无形的服务（如我们使用的运营商的通话、上网服务）。



## 3 什么是数据产品

明确了“什么是产品”这个问题后，回到数据产品这一概念上来。

数据产品作为产品的子集，在继承了产品“解决特定用户在特定场景下问题”的属性的同时，又具备了更多的“数据”属性。下面我分别从广义和狭义两个方面谈谈我对数据产品的理解。



### 3.1 广义上的数据产品

先说结论：从广义上说，所有的互联网产品都是数据产品。

为什么说所有的互联网产品都是数据产品，如果要详细解释这个问题，需要再写一篇专题来专门解释。

但是我们可以从产品的本质来理解这个说法。

产品的本质是什么？产品的本质是帮助用户解决特定场景下特定问题。

既然如此，那么所有的互联网产品都要有自己的`目标客户`,也都要面对自己的`目标用户`，没有`目标用户`的产品无异是空中楼阁。

既然如此，`目标用户`是谁？年龄、性别、职业、地理位置、收入范围、爱好、需求等是什么？

你看，无论什么行业什么领域，在进行产品设计与规划前是不是首先必须要收集这些用户数据，然后再基于这些用户数据进行产品规划与产品设计？

再说产品开发完成推向市场后，市场反应如何？用什么衡量呢？答案还是数据！

或者你对数据指标完全没有概念，好！抛开产品运营中的访问量、转化率、留存率等等数据指标，有多少用户使用了你的产品是不是必须要关心的？

所以说，在互联网时代所有的互联网产品都是数据产品这个说法一点也不夸张。这也是近些年数据驱动越来越被重视的原因。



### 3.2 狭义上的数据产品

一般而言，大多人理解或者认知的数据产品都是狭义上的数据产品。

这类数据产品的形态多种多样，而且种类庞杂，大到一个数据中心、小到一个数据api服务都可以看作数据产品。

我原本尝试着使用用户类型对数据产品分类，却发现很难实现，因为每一个数据产品都有自己的目标用户。这些用户有可能既是个人，又隶属于公司。而且对于不同岗位的人几乎都有适用的数据产品。

例如面对前端工程师的各种react组件，js组件，面对后端工程师的各种组件，面对Ui设计人员的图像渲染工具，面对数据分析师的数据分析工具或者平台等等。

后来读到《产品经理数据修炼30问》这本书，作者将数据产品根据数据生命周期分为以下四个层次：

* 数据采集层
* 数据接入层
* 数据处理层
* 数据应用层

其实作者将数据接入层也作为数据清洗和转换和存储的层级 。数据处理则是数据整合、格式化和预备分析的处理过程。

我不太赞同这一点，我的第一份工作就是数据处理工程师，其实数据的处理就是数据的整合、清洗、缺失处理和特征加工等流程，处理完成的数据一般会存放在数据库中。如果数据有专门的使用场景会再加一层业务使用逻辑，并建立相应的数据仓库，这个过程也是应该放在数据处理层面的。

不过这个根据数据生命周期对数据产品分类 的方法却值得借鉴，我在这个基础上，将数据产品分为四个体系

* 数据采集层面

  在这个层面的数据产品多为工具型产品，主要是从数据源获取数据。

  这个获取动作可以是主动采集，如使用爬虫程序爬取；也可以是被动接收，例如用户从手机APP或者网站上传照片，个人信息等等。

  代表产品有早期的QQ空间相册上传工具，部分数据公司的互联网爬虫程序等等。

  

* 数据处理层面

  在数据处理层面的产品也多为工具型产品，主要是对从数据采集层面获取的数据进行整合、清洗、缺失值处理和特征加工等。如果这些数据已经有具体的使用场景，还会针对不同场景下的业务建立相应的数据处理逻辑。

  代表产品一般为各互联网公司数据部门的ETL框架或者组件，一般不对外公开，但是也有一部分公司将自己的ETL框架开源出来了，如Apache Airflow，链接：<https://github.com/apache/airflow。

  ![airflow工作界面](/img/airflow.png)

  

* 数据存储层面

  数据存储层面的产品一般是数据处理层面数据处理的结果，一般的产品形态为面向事务的数据库和面向业务的数据仓库。

  另外，部分金融科技公司或者具有征信资质的数据公司对外提供的纯数据服务，如企查查对外提供的工商信息查询服务、百融、同盾提供的反欺诈验证服务等，因为这种纯数据服务一般是在数据仓库上层架设一套服务程序对外输出数据，所以也可以认为是属于这个层面的产品，不过这些产品如果说要归并到数据应用层面，也是说得通的。

  ![企查查api服务界面](/img/qichacha_api.png)

* 数据应用层面、

  数据应用层面的产品形态是最为丰富的，绝大部分用户看到的一般都是数据应用层面的产品，其中报表平台恐怕是最为大众所熟悉的数据产品了。对数据应用层面的产品分类，我还未找到合适的标准，现仅将其分三类：数据分析产品、数据可视化产品和机器学习算法产品。

  这个分类标准是不严谨的，后续我会再深入研究后再进行修正。

  

我将这四个层面的数据产品的产品形态和代表产品进行了梳理，具体如下图所示：

![data_product_classify](/img/data_product_classify.png)



## 4 结语

现在已经是移动互联网的下半场了，未来必将是一个数据驱动的时代。

从广义上来说，所有的互联网产品都是数据产品。所有的产品经理也都是数据产品经理，
无论是从事数据产品设计的产品经理还是关注产品数据的产品经理。
从这个层面上，我认为，数据产品经理不是一个职位，而是一种思维方式，一种数据驱动产品设计和产品运营的思维方式。

也许，不久的未来，产品经理这个职业会消失，取之代之的是数据驱动相关的职位。







