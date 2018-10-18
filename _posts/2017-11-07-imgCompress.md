---
layout: post
title: 图片压缩
categories: [OC]
tags: [OC]
description: 图片压缩
---

<h3>从磁盘加载一张图片，使用UIImageView显示在屏幕上，需要经过的步骤</h3>

{% highlight ruby %}

1、从磁盘拷贝数据到内核缓冲区
2、从内核缓冲区复制数据到用户空间
3、生成UIImageView,把图像数据赋值给UIImageView
4、如果图像数据为未解码的PNG/JPG，解码为位图数据
5、CA捕获到UIImageView layer树的变化
6、主线程Runloop提交CA,开始进行图像渲染
  6.1 Core Animation进行字节对齐
  6.2GPU处理位图数据，进行渲染

{% endhighlight %}


<img src="{{ site.BASE_PATH }}/assets/post/imgCompress.svg" />
