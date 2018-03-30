---
layout: post
title: CAShapeLayer
categories: [iOS]
tags: CoreAnimation
description: CoreAnimation CAShapeLayer
---

<h3>CAShapeLayer属性</h3>

{% highlight ruby %}

strokeStart和strokeEnd
    
这两个属性的值在0~1之间，0代表Path的开始位置，1代表Path的结束位置。是一种线性递增关系。strokeStart默认值为0，strokeEnd默认值为1。这两个属性都支持动画。

{% endhighlight %}


<h3>CAShapeLayer code</h3>

{% highlight ruby %}

CAShapeLayer *layer = [CAShapeLayer layer];
    layer.frame         = myView.frame;                // 与showView的frame一致
    layer.strokeColor   = [UIColor blueColor].CGColor;   // 边缘线的颜色
    layer.fillColor     = [UIColor clearColor].CGColor;   // 闭环填充的颜色
    layer.lineCap       = kCALineCapSquare;               // 边缘线的类型
    layer.path          = path.CGPath;                    // 从贝塞尔曲线获取到形状
    layer.lineWidth     = 4.0f;                           // 线条宽度
    layer.lineDashPattern = [NSArray arrayWithObjects:[NSNumber numberWithInteger:2],[NSNumber numberWithInteger:13],nil];
    
{% endhighlight %}

<img src="{{ site.BASE_PATH }}/assets/post/pai.png" ></img>

<img src="{{ site.BASE_PATH }}/assets/post/halfpai.png" ></img>
