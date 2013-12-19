---
layout: post
title: 用Stata计算地理距离
categories: [经济学人]
tags: [Stata, econometrics]
---

有关空间和贸易的研究中经常需要用到两地之间的距离，一开始在 Google 地图上拿尺子量，费时费力不说，还非常不准确。

由于地球是个球体，所以地球上两个地点之间最短的距离并不是地图上的直线距离，而是经过这两个地点的大圆的劣弧，即「大圆距离」（great-circle distance），这也是航空和航海中实际使用的导航方式。

![大圆距离](http://ww3.sinaimg.cn/large/abb3ee10jw1dznq6x85u6j.jpg)

那就，用 Google 地球量呗~可是，还是很麻烦有没有！所以，关键时刻还是要祭出 Stata。

首先要安装两条命令，「geocode」和「geodist」。

```
ssc install geocode
```

```
ssc install geodist
```

把需要计算的地点名称（地址、城市、省份或邮编等）作为字符串变量导入，然后「geocode」命令就会利用 Google 地图的 API 来获取各个地点的经纬度。

```
geocode, city(cityname)
```

![geocode](http://ww2.sinaimg.cn/large/abb3ee10jw1dznr5h8ce2j.jpg)

得到经纬度数据之后，就可以用「geodist」命令来计算北京与其他城市之间的距离了，其中 sphere 选项就是告诉程序用大圆距离公式来计算。

```
geodist latitude longitude latitude_bj longitude_bj, gen(dist) sphere
```

![geodist](http://ww1.sinaimg.cn/large/abb3ee10jw1dznrepjkbkj.jpg)

更新：由于 Google Maps 更新 API 的缘故，「geocode」命令已经不能使用，需要改用「geocode3」命令，使用方法类似。

