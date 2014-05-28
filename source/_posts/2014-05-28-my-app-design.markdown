---
layout: post
title: "Android REST"
date: 2014-05-28 17:20:12 +0800
comments: true
categories: app_framework
---

##关于开发框架

总听到码农说的都是不要重复造轮子，然后巴拉巴拉一堆。</br>

我个人还是不推崇一开始就是使用框架，这类东西其实是在你实际编码中不断摸索，提炼出来的`精华`和`模块`,也是工作总结。</br>

再谈谈现有的开源项目

*	[Afinal](https://github.com/yangfuhai/afinal)
*	[xUtils](https://github.com/wyouflf/xUtils)
*	[ThinkAndroid](https://github.com/white-cat/ThinkAndroid)

这三个都是国内经验丰富的作者贡献出来的有兴趣可以看看。
但是里面的错误还是比较多的。


##关于`我的`框架

Google 在 2013的IO大会上提出了一套REST CLIENT 架构


<img src="/images/android_rest.png">


看到ContentProvider就不喜欢，平常的开发中一般很少用，一般直接`Dao+Model+Manager`或者`Domain+Dao` 的方式直接于数据库交互， A而且没有跨进程的需求，基本不使用ContentProvider。但ContentProvider为数据库的管理提供了更清晰的接口，应该也是有好处的。


我目前的开发用的组装框架:

*	Volly
*	Butterknife
*	OrmLite

###Volly

2013的IO上由Google官方推出的解决 NetWork的开源库
并且在Google Store等App上已经使用上了，比较成熟稳定的一个开源库
一个`ImageLoader`异步图片请求的升级版，加上一个可控的网络请求队列
`RequestQueue`，可以在整个App中只维持一个请求队列单例，而且可以中断请求！而且是Google官方推出的，一般要缓存图片到SD卡的话还要用到disklrucache这个库

###Butterknife

这是一个`ViewInject` 减少使用findViewById这样的语句，并且高效的是不是使用反射的技术，之持Adapter,Fragment中使用。这是国内那些框架所不能及的。是在编译时生成中间class文件。但是有点不人性话的地方是都要一个默认的(Id)，`AndroidAnotation`这个注入库可以很好的解决这个问题。

###OrmLite

这个就不多说了,操作数据库用的，基于反射和注解的方式来简化sql语句

## 开源库

接触开源也有比较旧了，项目中也引用了一些比较成熟的开源库。如果有能力。我也希望我也有一个成熟稳定的分享给大家~