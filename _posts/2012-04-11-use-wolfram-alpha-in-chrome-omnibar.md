---
layout: post
title: 巧用Chrome地址栏打造智能计算器
categories: [奇技淫巧]
tags: [Chrome, Wolfram Alpha, apps]
---

Google Chrome 浏览器的地址栏（Omnibar）功能非常强大，除了输入地址和搜索关键词之外还有很多用途，例如做一些简单的计算：

![地址栏](http://ww3.sinaimg.cn/large/659b5540jw1dv9duw24i0j.jpg)

只要在地址栏里输入算式，计算结果就会自动出现在下拉栏中。不过，很鸡肋的是，貌似只能做加法和乘法等最为简单的计算（这些我口算就好了，要你何用）。想要地址栏做更复杂的运算怎么办？自己动手，丰衣足食，让我们把地址栏打造成更加强大的计算器。

我们首先想到的就是知识搜索引擎 [Wolfram Alpha](http://www.wolframalpha.com/)，苹果的智能助手 Siri 的发布使她更加广为人知。

<strike>另外，我们还知道 Chrome 有一项十分贴心的小功能，就是你在任何网站进行搜索之后，Chrome 就会自动记录该网站的搜索引擎，并且提供在该网站内进行搜索的选项。

我们现在要做的就是打开 Wolfram Alpha，在搜索框里随便输入一个算式，比如「1+1」。然后我们回到 Chrome 的 Omnibar 搜索栏，在里面输入「wolframalpha」，这时，我们可以看到搜索栏右边会出现「按 Tab 可通过 Wolfram|Alpha 进行搜索」的提示。

按照提示按 Tab 键，我们会发现搜索栏变成下图的样子，这时我们就可以在 Chrome 的搜索栏里使用 Wolfram Alpha 了。

为了使用更加方便，我们可以打开右上角的扳手按钮进入 Chrome 选项，在「基本设置-搜索-管理搜索引擎」里将 Wolfram Alpha 的快捷键改为「wa」（或者其它方便的字符），这样，我们就在 Chrome 的搜索栏输入 wa Tab 三个键之后就可以直接利用 Wolfram Alpha 搜索。</strike>

现在，我们只需要安装一个 [Chrome 扩展](https://chrome.google.com/webstore/detail/icncamkooinmbehmkeilcccmoljfkdhp)就可以轻松地在 Chrome 里使用 Wolfram Alpha 了。使用方式有两种，第一种是直接点击扩展栏上的按钮，另一种是直接在地址栏里键入 `= + Space` 或者 `= + Tab`。

![扩展](http://ww1.sinaimg.cn/large/abb3ee10tw1e6r239dwkgj20dw06ot9d.jpg)

那么，利用 Wolfram Alpha 可以搜索什么？只怕你想不到，不怕她做不到。我们随便举几个例子，其它数不清的强大功能就有待自己发掘了。

如果你想算一个二次积分，那么只需要输入「[int  x^2y+x,  y=2..4, x=1..3](http://www.wolframalpha.com/input/?i=int++x%5E2y%2Bx%2C++y%3D2..4%2C+x%3D1..3)」，就能得到：

![二次积分](http://ww1.sinaimg.cn/large/659b5540jw1dv9efhkt7lj.jpg)

如果你想了解一下美帝人民水深火热的失业率，那么只需要输入「[chicago nyc unemployment](http://www.wolframalpha.com/input/?i=chicago+nyc+unemployment)」，就能得到：

![失业率](http://ww3.sinaimg.cn/large/abb3ee10jw1dv9ftmjj4mj.jpg)

如果你想知道吃一个巨无霸是多么罪大恶极，那么只需输入「[1 big mac](http://www.wolframalpha.com/input/?i=1+big+mac)」，就能得到：

![热量](http://ww1.sinaimg.cn/large/abb3ee10jw1dv9ftvpeq1j.jpg)

如果你想知道今天要不要涂防晒霜，那么只需输入「[uv index](http://www.wolframalpha.com/input/?i=uv+index)」，就能得到：

![UV](http://ww1.sinaimg.cn/large/abb3ee10jw1dv9ftz9ixej.jpg)

最后，如果你想勾搭妹子，那么只需叫她用 Wolfram Alpha 搜索这个：

[ContourPlot3D[(x^2 + (9/4) y^2 + z^2 - 1)^3 - x^2 z^3 - (9/80) y^2 z^3 == 0, {x, -2, 2}, {y, -2, 2}, {z, -2, 2}]](http://www.wolframalpha.com/input/?i=ContourPlot3D%5B%28x%5E2+%2B+%289%2F4%29+y%5E2+%2B+z%5E2+-+1%29%5E3+-+x%5E2+z%5E3+-+%289%2F80%29+y%5E2+z%5E3+%3D%3D+0%2C+%7Bx%2C+-2%2C+2%7D%2C+%7By%2C+-2%2C+2%7D%2C+%7Bz%2C+-2%2C+2%7D%5D)

嗯哼。
