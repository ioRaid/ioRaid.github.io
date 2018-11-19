---
layout: post
title: self super 区别 
categories: [oc]
tags: [oc]
description: self super 区别 
---

<h3>[self class]和[super class]的区别</h3>

{% highlight ruby %}

当使用[self class]时，这时的self是Son，在使用objc_msgSend时，第一个参数是receiver也就是self，也是 Son* son这个实例。
第二个参数，要先找到class这个方法的selector，先从Son这个类开始找，没有，
然后到Son的父类 Father中去找，也没有，再去Father的父类NSObject去找，一层一层向上找之后，
在NSObject的类中发现这个class方法，而 NSObject的这个class方法，就是返回receiver的类别，所以这里输出Son。

当使用[super class]时，这时要转换成objc_msgSendSuper的方法。先构造objc_super的结构体吧，第一个成员变量就是self,
第二个成员变量是Father，然后要找class这个selector，先去superClass也就是Father中去找，没有，
然后去Father 的父类中去找，结果还是在NSObject中找到了。然后内部使用函数objc_msgSend(objc_super->receiver, @selector(class)) 去调用，
此时已经和我们用[self class]调用时相同了，此时的receiver还是Son* son，所以这里返回的也是Son。


{% endhighlight %}


<a href="https://blog.csdn.net/Loving_iOS/article/details/49884599">参考</a>
