# 第四章 背景图像效果

设置背景图像，并在每个标题上添加一个项目符号
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter4/QQ%E6%88%AA%E5%9B%BE20160721085927.png)

在使用像素设置背景时，指定图像垂直和水平多少像素，定位的是背景的左上角，而使用百分比，则是背景的百分比的位置。

最好不要混合使用像素和百分比，可能会使css失效
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter4/Image.png)

园角框

    1. 对于固定宽度的圆角框，可以用两个图像

 背景设置图像相同的颜色

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter4/Image%20%282%29.png)

这种方法是对于单色而没有边框是有效的。
2.不在框中设置背景颜色，而是设置重复显示
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter4/Image%20%283%29.png)

应用了样式的固定宽度框，框内的字体大小改变，框的宽度不会改变，高度会随着文本的尺寸而进行改变。

灵活的圆角框
加大文字尺寸，宽度和高度会跟着改变，
采用滑动门技术：使一个图像在另一个图像上滑动，另一个图像的一部分被遮盖起来。
这个方法需要4个图像：两个顶部图像组成顶部曲线，两个底部图像组成底部曲线和框的主体。顶部图像的高度必须与框的最大高度相同。


山顶角
可以创建线形的位图角蒙版，蒙版区域盖住你正使用的背景颜色，而角区域实际上是透明的。当放在有颜色的框上，他们形成曲线形框的效果。

1多背景图像，在四个角设置圆角框，分别安放在四个角的位置中
2使用css中的border-radius属性可以设置圆角框
3.采用css3新特性border-image属性，浏览器会自动地将图像划分为9个单独的部分，这种技术称为九分法缩放。在距离框的顶部和底边25%的地方画两条线，再在距离左边和右边的25%的地方画两条线，border-image属性会自动地把图像的每个部分用于对应的边框，如果图像不够大，可自动地平铺，产生一个可扩展的框

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter4/Image%20%284%29.png)

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter4/Image%20%285%29.png)

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter4/Image%20%286%29.png)

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter4/Image%20%287%29.png)

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter4/Image%20%288%29.png)

投影
1可以使用背景图像阴影表示，再div中插入背景图像投影，使用浮动让div收缩包围阴影图像
使用图像负的外边距来设置投影的偏移量，也可以使用相对定位来偏移图像

直接使用css box-shadow属性来设置投影

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter4/Image%20%289%29.png)

3px向下偏移，3px向右偏移 6px代表宽度，#666代表阴影颜色

不透明度：
属性：opacity 0-1 1表示不透明度为100%

RGBa （0,0,0,0.8） 前面3个数值表示红绿蓝的值 最后是不透明度的值

png透明
png格式的文件可以支持透明，但IE6不直接支持

css的视差效果：

```
<title>Parallax Effect | Chapter 4 | CSS Mastery </title>
</head>
<style type="text/css">
<!--
/* pretty */

.content {
    max-width: 61em; /* 1098px */
    margin: 0 auto;
    padding: 100px 20px 0 20px;
}


/* parallax effect */

body {
  background-image: url(img/bg-rear.gif);
  background-repeat: repeat-x;
  background-color: #d3ff99;
  background-position: 20% 0;
}

.midground {
  background-image: url(img/bg-mid.png);
  background-repeat: repeat-x;
  background-color: transparent;
  background-position: 40% 0;
}

.foreground{
  background-image: url(img/bg-front.png);
  background-repeat: repeat-x;
  background-color: transparent;
  background-position: 150% 0;
}
-->
</style>
</head>

<body>
  <div class="midground">
    <div class="foreground">
      <div class="content">
        <h1>Your content will go here!</h1>
      </div>
    </div>
  </div>
</body>
</html>
```

图像替换： 图像替代，就是像我们在平时将文本添加到文本中，然后通过css隐藏文本在它的位置上显示一个背景图片，这样，搜索引擎仍然可以搜到HTML文本，即使我们禁用css后，文本时仍然是可以显示的。
众所周知，HTML文本由很多的优点。文本可以被搜索引擎读取，开发人员可以对其进行复制和粘贴，并且在浏览器中改变字体大小后，它也会改变。因此很多设计人员都想尽量的采用HTML文本而不是文本的图像，但是遗憾的是，页面设计人员对于文本有有限的选择，尽管可以通过css来控制版面但是有很多字体的效果是无法实现的，所以在某些情况下还是需要用文本的图像的。
1、FIR 有TODD FAHRNER 开创是最早流行的图像替代技术，因为它具有严重的可访问性问题，所以应尽量避免这个技术。
2、PHARK 由MIKE RUNDLE 发明的一种适合屏幕阅读器的图像替代技术，而且不需要添加额外的标签。
3、 GILDER/LEVIN 由TOM GILDER AND LEVIN ALEXANDER 一起发明的，解决了阅读器的支持，关闭图像打开css是无效。
4、SPRITES 由于游戏视频等画质越来越高必须有一种技术可以智能的的处理材质和贴图，并且同时要保持画面流畅。所以这种技术它将很多图片组合到一个网格上，然后通过程序将每个网格内容定位到画面上。




