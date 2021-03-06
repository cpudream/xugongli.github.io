---
layout:     post
title:      "获取中国指定行政区域内所有POIS(兴趣点)的方法"
subtitle:   "基于高德地图和百度地图开放api的实现方式"
date:       2018-10-30 22:37:15
author:     "soaringsoul"
header-img: "img/posts/default_post.jpg"
catalog: true
tags:
    - My GitHub Projects

---

项目地址：

早在2017年5月，曾经在知乎上写过一篇文章[获取一个城市全部道路名的方法总结](https://zhuanlan.zhihu.com/p/26952109)，总结了下当时对`如何获取一个城市全部道路名`的探索。

当时提出了两个方法，其中之一为：

----------

* 从高德地图获取该城市的行政区域边界经纬度


* 根据转换后的经纬度坐标找到经纬度中最大值点和最小值点，生成该多边形区域的外切矩形。

   ![split_examples_before](/img/posts/split_examples_before.jpg)

* 把外切矩形分成若干个小矩形。

![split_examples](/img/posts/split_examples.jpg)


> 注：目百度地图web api接口的限制，一次最多只能返回某一个矩形区域内的400条数据，所以要把外包矩形分成若干个小矩形

* 利用百度地图Place Api接口，在该矩形区域以“道路”为关键字在每个矩形区域内搜索。并存储获取到的道路名和经纬度。

----------

不过当时在使用这个方法的过程中遗留了下面三个问题：

----------

*  获取一个城市的经纬度边界后，只生成了该多边形的外包矩形，无法准确判断获取的点是否在这个多边形区域内，而且如果一个城市如果区域为狭长形，如上图示的内蒙古自治区，这个矩形内的大部分区域其实都是非目标区域，而且这样采集下来耗时会非常久

* 因为未能解决`如何判断一个点是否在一个凹多边形内`的问题，所以必须对采集到的所有兴趣点进行存储，而且无法根据经纬度判定其是否在指定的行政区域内
* 切割矩形时无法预测切割后的小矩形区域内的兴趣点数量是否小于400，精度设置需要经过多次采集后根据采集结果来评估，比较耗时。

----------

后来，通过不断的探索和研究完善了这个程序，解决了以上这些问题，核心解决方案如下：

1.前两个问题的解决方法获取城市或者区县的经纬度边界后，首先仍是作它的外切矩形，但是不再直接设置精度来切割，而是使用递归的方法来切割，具体方法如下：

* 第一步，将这个外切矩形分成2*2即四个矩形，如下图示：

![split_examples_2x2](/img/posts/split_examples_2x2.jpg)


* 第二步，分别判断这四个矩形区域返回的指定关键词的兴趣点个数是否>=400，如果大于等于400，使用递归再次将这个分割后的矩形区域一分为四，直至每个矩形区域返回的兴趣点个数小于400，然后将每个最终分割完成后小矩形区域的区域坐标（其实就是对角线两端坐标）加入到一个`列表`中

![split_examples_end](/img/posts/split_examples_end.jpg)


* 第三步， 遍历列表获取指定关键词的兴趣点个数，并在存储时可以根据采集到的兴趣点的经纬度判断其是否在指定的行政区域内，进而可以选择是否存储。

2.对于遗留的第三个问题通过`shapely`这个地理区域库来解决的，`shapely`可以根据指定的多边形区域坐标生成一个多边形，然后提供了一个`shapely.Polygon.contains(Point)`方法用来判定指定的`Point`是否在这个区域内，无论是凸多边形，还是凹多边形。


相关程序源代码已经提交到，[我的GitHub](https://github.com/xugongli)


[采集程序源码](https://github.com/xugongli/china_region_pois_spider)
