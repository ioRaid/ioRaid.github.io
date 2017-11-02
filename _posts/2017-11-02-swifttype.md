---
layout: post
title: Enums-structs-classes
categories: [swift]
tags: [swift]
description: swift 六大类型
---

<h3>class struct 之间区别</h3>

对于Circle（使用struct定义）

{% highlight ruby %}

var a = Circle（）
a.radius = 60.0 
var b = a
a.radius = 1000.0   // b.radius仍然具有值60.0

{% endhighlight %}

对于Circle（使用类定义）：

{% highlight ruby %}

var a = Circle（）   // a class based circle 
a.radius = 60.0 
var b = a
a.radius = 1000.0   // b.radius也变为1000.0

{% endhighlight %}

使用 value types 创建对象时，会复制。使用引用类型（class）时，新变量引用相同的对象。

<h3>class struct enum 异同</h3>
相同：提供封装，具有初始化方法，具有计算属性，可以使用协议，and they can be modeled retroactively.
enum:值类型，不能有存储属性
struct：值类型，具有存储属性
class:引用类型，具胡存储属性。
