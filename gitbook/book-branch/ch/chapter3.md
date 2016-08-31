# 第三章：可视化格式模型

盒子模型：
它由元素的内容，内边距，边框和外边距组成。

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter3/Image.png)

外边距可以使负值

在IE的早期版本，在混杂模式中使用自己的非标准盒模型。它的width属性不是内容的宽度，而是内容，内边距，和边框的宽度总和。

最好的解决方案是回避这个问题，不要给元素添加具有指定宽度的内边距，而是尝试将内边距或外边距添加到元素的父元素和子元素

外边距的叠加：
但两个或更多的外边距相遇时，它们将形成一个外边距，这个外边距的高度等于两个发生叠加的外边距的高度中的较大者
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter3/Image%20%282%29.png)

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter3/Image%20%283%29.png)

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter3/Image%20%284%29.png)

**只有普通文档流中块框的<font color=red>垂直</font>外边距才会发生外边距叠加。行内框，浮动框或绝对定位框之间的外边距不会叠加**

## 3.2定位概述
### 3.2.1 可视化格式模型

块级元素：p,h1,div 行内元素：strong,span
可以通过display的属性来改变生产框的类型。将display设置成block可以让行内元素表现得像块级元素一样，设置成inline表现为行内元素，none即框和内容不显示。

定位机制：普通流，浮动和绝对定位。普通流中的元素框的位置由元素在HTML中的位置决定
行内框在水平排列，可以使用水平内边距，边框和外边距来调整他们的水平间距，但不能通过调整垂直内边距，边框和外边距，它们不影响框内的高度，但是行高可以增加这个框的高度。
将display设置成inline-block可以让元素像行内元素一样水平地依次排列，但是框的内容仍然符合块级框的行为，可以设置水平和垂直的内边距，外边距，高度和宽度。

#### 相对定位：（属于普通流定位模型的一部分）
可以通过设置position：relative 设置垂直和水平的位置，让这个元素相对于它的起点移动。

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter3/Image%20%285%29.png)

#### 绝对定位：（与文档流无关）
设置：position:absolute   设置宽度和高度 位置是相对于距离它最近的那个已定位的祖先元素确定的。如果元素没有已定位的祖先元素，它的位置是相对于初始包含快的，包括画布或html元素。
绝对定位的框与文档流无关，所以可以覆盖页面上的其他元素，通过设置z-index属性来控制这些框的叠放次序。

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter3/Image%20%286%29.png)

#### 固定定位：fixed（是绝对定位的一种）
它的祖先元素的包含块是视口（浏览器窗口），可以在页面滚动时一直出现在屏幕上的固定位置。
IE6或更低的版本不支持这个属性。

#### 浮动：
不在文档的普通流中，所以文档的普通流在排列时忽略它的存在。

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter3/Image%20%287%29.png)

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter3/Image%20%288%29.png)

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter3/Image%20%289%29.png)

行框和清理：
浮动会让元素脱离文档流，如果浮动的元素后面有一个文档流，那么这个元素的框会表现得像浮动根本不存在一样，但是框内的内容会受到浮动的影响，会移动流出空间。文本围绕图像。

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter3/Image%20%2810%29.png)

要想阻止行框围绕浮动框外边，可以使用clear属性，包括left，right，both，none。
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter3/Image%20%2811%29.png)
浮动元素脱离了文档流，不影响周围的元素，但是对于进行清理实际上为前面的浮动元素流出了垂直空间。

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter3/Image%20%2812%29.png)

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter3/Image%20%2813%29.png)

因为浮动元素脱离了文档流，所以保卫图片和文本的div不占据空间，需要在div末尾添加一个带有属性clear的空div，来迫使容器元素包围浮动元素
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter3/Image%20%2814%29.png)

但这样做添加了不必要的代码
还可以选择浮动容器div

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter3/Image%20%2815%29.png)

然而这样的缺点使下一个元素会受到这个浮动元素的影响。为了解决这个问题，有些人选择浮动布局中几乎所有东西，然后使用合适的元素对这些浮动元素进行清理，虽然有助于减少或清除不必要的标记，但浮动会变得复杂。

overflow属性在使用hidden或auto时有一个副作用，会自动清理包含的任何浮动元素，因此这是一种有用的元素清理方法，不需要添加额外的标记，但这种方法会在某些情况下产生滚动条或截断内容

使用css生成的内容或JavaScript对浮动元素进行清理，不直接向标记中添加进行清理的元素，而是将它动态地添加页面中，对应清理的元素，常常添加一个类名。

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter3/Image%20%2816%29.png)

用after伪类和内容声明在指定的现有内容的末尾添加新的内容，不占据垂直空间将高度设置为0，设置为不可见，需要将display设置为block，变成块级元素，换行，这样设置后，就可以对生成的内容进行清理。


