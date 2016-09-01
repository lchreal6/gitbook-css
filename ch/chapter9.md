# 第九章 bug和修复bug

在认为是浏览器的bug之前先确认是否来源于自己的css或是对css规范的理解不完整所导致的。
常见的css问题：
通常是打字和语法造成的错误，可以选择一个包含语法突出显示和代码补全功能的css编辑器，如SKEdit或CSS Edit.也可以通过CSS Validator 服务运行代码可以突出显示所有语法错误。

特殊性和分类次序问题：
将一个规则应用于一个元素时，发现没有效果，这时往往存在特殊性问题。可以应用其他规则而且他们会正常工作，但是某些规则似乎不起作用，问题往往是已经在文档的其他地方使用更特殊的选择器为这个元素定义了规则。

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter8/Image.png)

想在intro段落上应用规则，然而因为选择器的特殊性，intro无法应用，被 .content p 选择器覆盖。
解决方法：

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter9/Image%20%282%29.png)

让选择的intro段落的选择器更特殊。

外边距叠加问题

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter9/Image%20%283%29.png)

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter9/Image%20%284%29.png)

效果不是理想那样，这是因为，没有将子元素设置为内边距和边框，那么久默认地将子元素的顶部边距和底部边距与父元素的外边距叠加，得出20px外边距，而这一外边距却是包含在父元素之外的。

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter9/Image%20%285%29.png)

为了让前面的示例看起来像图 9-3，只需在div周围中添加内边距和边框。
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter9/Image%20%286%29.png)

捕捉bug的基本知识
尽量在更为标准符合w3c的浏览器中开发和测试，那么它很可能在所有符合标准的浏览器中都会表现正常。在项目开发过程中用所有主流浏览器检查页面。

尽量一开始就避免bug，应该尽量使用简单的代码实现所需要的结果，避免使用过分花哨的技术。绝对必需的时候才使用hack

隔离问题：
隔离问题的一种方法是在相关元素上应用边框或轮廓。
还有的是将position设置为relative，将display属性设置为inline

创建基本测试案例。就是重现所需的最少量的HTML和CSS。


拥有布局
Window上的IE使用布局概念来控制元素的尺寸和定位。哪些“拥有布局”的元素负责本身及其子元素的尺寸设置和定位。如果一个元素“没有拥有布局”，那么它的吃醋呢位置由最近的拥有布局的祖先元素控制。

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter9/Image%20%287%29.png)

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter9/Image%20%288%29.png)

布局是许多IE显示bug的根源。


解决方法：
IE条件注释
关于hack和过滤器的一个警告
明智地使用hack和过滤器
应用IE for Mac 带通过滤器
应用型号HTML hack
应用子选择器hack

常见的bug及其修复方法
都是IE6或以下的版本所存在的bug

1.双边距浮动bug
2.3像素文本偏移bug
3.IE6重复字符的bug
4.IE6的“藏猫猫”bug
5.相对容器中的绝对定位

浏览器的分级支持
