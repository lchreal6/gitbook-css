# 第八章 布局


css布局技术的根本是3个基本概念：定位，浮动和外边距操纵

设计布局：
在将设计转换为功能完整的模板时，理应在图纸上画好设计图。先将页面划分为大的结构趋于，比如容器，页眉，内容区域和页脚。结构设计之后，可以关注不同类型的内容。找出模式并确定命名约定之后，最好马上定义使将使用的元素，几下颜色的编码和尺寸。

设置基本结构：
使用外边距居中，可以这样. margin:0 auto;

但IE6不支持以上格式居中，而在IE6中将text-align：center 误解为所有东西居中，而不只是文本。方法是让主体标签中的所有东西居中，包括容器div，让后让容器的额内容重新向左对齐。

两列浮动布局
基于浮动的布局是最容易使用，也是最可靠的。因为浮动的元素不占据文档流中的任何空间，他们就不再对包围他们的块框产生任何影响。为了解决这个问题，需要对布局中各个点上的浮动元素进行清理。非常常见的做法是不是连续第浮动和清理元素，而是浮动几乎所有东西，最后在整个文档的“战略点”（比如页脚）上进行一次或两次清理。还可以使用溢出方法清理某些元素的内容。这是作者最喜欢的做法。

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter8/Image.png)

创建两列浮动，一般都是将两列向左浮动，然后使用外边距或内边距在两列之间创建一个隔离带。在使用这种方法时，列在可用空间内包的很紧，如果元素内容太大，在IE中整个元素就会扩展，就没有足够的空间并排，为了防止这种情况可以不使用水平外边距或内边距来建立隔离带，而是一个向左浮动，另一个向右浮动。

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter8/Image%20%282%29.png)
因为元素是浮动的，它们不再在文档流中占据任何空间，这会导致页脚向上升，为了避免这种情况，需要对它们的父元素应用溢出方法，从而清理浮动元素。

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter8/Image%20%283%29.png)

三列浮动布局
创建三列浮动布局所需要的HTML与两列布局的HTML非常相似，唯一的差异是在内容div中添加了两个新的div；一个用于主内容，另一个用于次要内容。可以重用灵活的primary和secondary类名

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter8/Image%20%284%29.png)
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter8/Image%20%285%29.png)

注意，第一个示例中主div中添加的右内边距现在要应用在第二个示例的主div上。因此，需要从一般样式中删除内边距，把它应用于更特定的样式。

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter8/Image%20%286%29.png)

固定宽度，流式和弹性布局
固定宽度可以使开发人员对布局和定位有更大的控制力，但是也有确定，无论窗口有多大，它们的尺寸总是不变的。因此，它们无法充分利用可用空间。

为解决问题，可以使用流式布局
流式布局是相对于浏览器的窗口进行伸缩。但是也有确定，在窗口宽度较小时候，行变得非常窄，好难阅读，需要添加以像素或em为单位的min-width，从而防止布局变得太窄。

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter8/Image%20%287%29.png)

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter8/Image%20%288%29.png)

弹性布局：
虽然流式布局可以充分利用可用的空间，但是在大分辨率显示器上，行仍然会过长，让用户不舒服，相反，在窄窗口中或者增加文本字号时，行会变得非常短，内容很零碎。
弹性布局相对于字号来设置元素的宽度，可以确保在字号增加时整个布局随之扩大。字号减少是，布局也会缩小。
让1em相当于10元素
建议yiem设置容器的宽度，内部宽度仍然使用百分数，这样的话内部宽度仍然是相对于字号的。这样就可以方便地修改布局的总尺寸，不必修改每个元素的宽度。这种结局方案更灵活，更容易维护。

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter8/Image%20%289%29.png)

流式和弹性图像：
选择使用流式或弹性布局，那么固定宽度的图像就会对设计产生强烈的影响。

对于跨度大区域的图像，比如站点页眉或品牌区域中的图像，可以考虑使用北京图像而不是图像元素，随着元素的伸缩，背景图像可以或多或少地露出来。

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter8/Image%20%2810%29.png)

如果图像用作页面上的图像元素，那么将容器元素的宽度设置为100%并且将overflow属性设置为hidden，右边被截短，不会随着布局伸缩。
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter8/Image%20%2811%29.png)
对于常规图像，可以设置图像的百分数宽度，并且添加与图像宽度相同的max-width以避免像素失真。

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter8/Image%20%2812%29.png)
faux 列
理想情况下，背景应该拉长到整个布局的最大高度，从而形成列的效果。但是，因为导航元素和次要内容趋于没有扩展到最大高度，所以它们的背景也不会拉长。
为了创建列的效果，需要创建一个伪列。方法是在一个占据布局最大高度的元素上重复应用背景图像。

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter8/Image%20%2813%29.png)

流式布局创建faux列就有点复杂。简历faux列的技巧是按百分比对背景图像进行定位。
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter8/Image%20%2814%29.png)

高度相等的列
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter8/Image%20%2815%29.png)

为了把列的底边定位在正确的位置，需要让它们与齐容器元素的底部对齐。为此，首先把容器的position设置为relative，再把空div的position设置为absolute，把它们的bottom属性设置为零。现在，只需设置正确的宽度和高度，应用底部背景图像

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter8/Image%20%2816%29.png)

也可以用css3 创建等高文本列，通过columm-count,columm-width和column-gap
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter8/Image%20%2817%29.png)

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter8/Image%20%2818%29.png)

CSS框架和CSS系统

