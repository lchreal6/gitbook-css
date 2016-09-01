# 第十章：实例研究 Roma Italia

在编写标记时，考虑的重要因素是应该尽可能有意义而且尽可能轻量。
“有意义”：是指我们选择的html元素和选择器名称应该以适当的方式表示内容，让内容的层次关系和结构在去掉所有样式的情况下仍然有意义。
“轻量”：是指对于各种标记html元素，属性和值，css的选择器，属性和值，能简化就简化

reset.css
在开头声明几个“全局”变量，这是因为在不同的浏览器中默认的样式可能不一样。
可以在reset.css中设置默认的样式，再通过master.css导入

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter10/Image.png)

box-shadow ，rgba，text-overflow属性

字体链接和更好的排版

标点符号的悬挂


![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter10/Image%20%282%29.png)

@font-face
让我们在设计中使用任何字体显示html文本，而不需要考虑用户的机器上是否安装了这种字体。这通常称为字体链接或字体嵌入。

cufon

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter10/Image%20%283%29.png)

利用ajax和jquery实现搜索功能


