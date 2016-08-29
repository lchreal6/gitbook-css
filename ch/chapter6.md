# 第六章 对列表应用样式和导航条

添加定制的项目符号，可以使用list-style-image属性，但是这种方法对项目符号的图像位置控制机不强，更常用的是关闭项目符号，并且将定制的项目符号作为背景添加在列表元素上。

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter6/Image.png)
基本的垂直导航

```
ul.nav {
  margin: 0;
  padding: 0;
  width: 8em;
  list-style-type: none;
    float: left;
    background-color: #8BD400;
    border: 1px solid #486B02;
    border-bottom: none;
}

ul.nav li {
  display: inline: /* :KLUDGE: Removes large gaps in IE/Win */
}

ul.nav a {
  display: block;
    color: #2B3F00;
  text-decoration: none;
    border-top: 1px solid #E4FFD3;
    border-bottom: 1px solid #486B02;
  background: url(img/arrow.gif) no-repeat 5% 50%;
    padding: 0.3em 1em;
}
```

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter6/Image%20%282%29.png)

在垂直导航条中突出显示当前页面

可以利用css的选择器特性，在页面的主体上添加该页面的特有的id 再通过css修改导航对应该页面的样式，来突出显示用户所处于的页面。
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter6/Image%20%283%29.png)
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter6/Image%20%284%29.png)
创建简单的水平导航条
一样需要将内边距和外边距设置为0
block：inline
前一页 和后一页的类为 rel ：prev  和rel ：next
应用：before和：after伪选择器 以及content属性 可以在前一页和后一页的导航条中添加箭头

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter6/Image%20%285%29.png)
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter6/Image%20%286%29.png)

创建图形化导航条：

```
ul.nav.li{
float:left
}
```

列表由垂直显示变为水平显示。但记住，当元素浮动时，它不占据文档流中的任何空间，因此，父元素实际没有任何内容，它就会收缩，从而会隐藏列表背景。可以有几种方法让父元素包含浮动的子元素。1添加一个进行清理的元素2让父元素浮动，并且使用某个元素对它进行清理以便换行3使用overflow：hidden技术

滑动门技术：
用一个大图像和一个侧边图像创建标签页，随着标签页中文本的扩展，大图像的更多部分露出来，较小的图像留在左边，盖住大图像的硬边缘。

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter6/Image%20%287%29.png)
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter6/Image%20%288%29.png)
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter6/Image%20%289%29.png)

这样随着文本大小的改动，标签页依然可以自由地进行扩展，而不会被限制。

Suckerfish 下拉菜单
只需把子导航嵌套在无序列表中，把列表定位到屏幕之外，然后当鼠标悬停在父列表上时重新定位它。

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter6/Image%20%2810%29.png)

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter6/Image%20%2811%29.png)
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter6/Image%20%2812%29.png)

CSS图像映射
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter6/Image%20%2813%29.png)
将图像的一些区域作为热点，点击图像的某个位置可以打开连接或实现某些指示

```
<div class="imagemap">
<img src="img/nerdcore.jpg" width="333" height="500" alt="Some of the Clearleft team" />
<ul>
<li class="rich"><a href="http://www.clagnut.com/" title="Richard Rutter">Richard Rutter</a></li>
<li class="sophie"><a href="http://www.wellieswithwings.org/" title="Sophie Barrett">Sophie Barrett</a></li>
<li class="cath"><a href="http://www.electricelephant.com/" title="Cathy Jones">Cathy Jones</a></li>
<li class="james"><a href="http://www.jeckecko.net/blog/" title="James Box">James Box</a></li>
<li class="paul"><a href="http://twitter.com/nicepaul" title="Paul Annett">Paul Annett</a></li>
```

需要将div的position属性设置为relative，而 a的position设置为absolute

```
    .imagemap {
  width: 333;
  height: 500;
  position: relative;
}
```

```
    .imagemap a {
  position: absolute;
    display: block;
    background-image: url(img/shim.gif);
  width: 50px;
  height: 60px;
  text-indent: -1000em;
}
```
将所有锚定位到图像的左上角，然后使用top和left的定位属性，将每个热点定位到图像中相关的人身上。

```
.imagemap .rich a {
  top: 50px;
  left: 80px;
}

.imagemap .sophie a {
  top: 90px;
  left: 200px;
}

.imagemap .cath a {
  top: 140px;
  left: 55px;
  width: 60px;
  height: 80px;
}

.imagemap .james a {
  top: 140px;
  left: 145px;
}

.imagemap .paul a {
  top: 165px;
  left: 245px;
  width: 60px;
  height: 80px;
}
```

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter3/Image%20%2814%29.png)

```
.remote a .link {
  position: absolute;
  display: block;
  width: 10em;
  right: -11em;
    cursor: pointer;
}

.remote .rich a .link {
  top: 0;
}

.remote .sophie a .link {
  top: 1.2em;
}

.remote .cath a .link {
  top: 2.4em;
}

.remote .james a .link {
  top: 3.6em;
}

.remote .paul a .link {
  top: 4.8em;
}
```





