# 第五章 简单的链接样式

简单的链接样式

< a > 可以作为内部引用 和外部链接
伪类选择器：
：link 用来寻找没有被访问过的链接；
 :visited寻找被访问过的链接
 :hover 寻找鼠标悬停处的元素
为了提高页面的可访问性，在定义鼠标状态时，最好添加focus类，通过键盘移动到链接时，会与鼠标悬停产生相同的样式。
 :active 寻找被激活的元素 即链接被单击

选择去掉下划线可以设置text-decoration属性 ：none

选择器的次序非常重要，这是由于层叠造成的，当两个规则具有相同的特殊性，后定义的规则优先。
所以最好按照以下次序应用链接样式：
a:link , a:visited , a:hover ,a: foucs, a:active;
记忆：Lord Vader Hates Furry Animals

下划线样式
可以替换成不太刺眼的点线，利用边框创建下划线

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter5/Image.png)

也可以插入背景图像和gif
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter5/Image%20%282%29.png)

为链接布标设置样式：
可以使用：target 属性 当点击锚点页面转到目标元素时，目标元素的样式会出现变化，这样让用户容易看出


突出显示不同类型的链接
让不同类型的链接可以添加不同的样式以示区别，例如添加右上角的背景图像
如外部链接可以添加外部链接的图标，用属性类选择器来筛选出具有http:链接的外部链接
class[href^="http:"] 表示 开头有http：的属性的链接
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter5/Image%20%283%29.png)

但有些外部链接是指向内部域名的，可以将他们的样式删除
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter5/Image%20%284%29.png)

突出显示可下载的文档和提要：可用a[href$=".pdf"] 表示结尾为pdf格式的外部链接
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter5/Image%20%285%29.png)


图像翻转：
设置3个不同背景颜色的图像作为背景，一个是正常状态，一个是悬浮状态，一个是激活转态，不同状态设置不同颜色的背景图像，当鼠标执行时不切换，产生图像翻转。
![enter image description here](http://ocjqhfs9p.bkt.clouddn.com/img/chapter5/Image%20%286%29.png)

多图像的缺点使，在浏览器第一次加载鼠标悬停的图像时有短暂的延迟。会造成闪烁的效果。

Pixy样式的翻转：
不切换多个图像，而是使用一个图像并切换它的背景位置。好处是减少了服务器的请求数量，可以将所有按钮状态放在一个地方。
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter5/Image%20%287%29.png)
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter5/Image%20%288%29.png)

css精灵
使用pixy方法可以减少服务器的请求数量，那样更进一步地把所有图标都放在一个图像，利用pixy方法对齐图像即可。
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter5/Image%20%289%29.png)

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter5/Image%20%2810%29.png)

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter5/Image%20%2811%29.png)

css3 包含text-shadow，box-shadow，border-raidus 和gradient（渐变）  box-reflect（倒影）属性
可以利用这些属性设置按钮样式
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter5/Image%20%2812%29.png)

纯css工具提示：
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter5/Image%20%2813%29.png)

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter5/Image%20%2814%29.png)

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter5/Image%20%2815%29.png)


