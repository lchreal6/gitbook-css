# 第七章 对表单和数据表单应用样式

对数据表格应用样式
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter7/Image.png)

表格特有的元素
1.summary和caption
caption属性用作表格的标题
summary用于表格标签，和图像的alt属性类似

2 thead tbody 和 tfoot
 th用于行列标题 tr表示表格的行元素 td 表示行元素的单个元素

3col和colgroup
colgroup能够使col元素对一个或多个定义和分组。

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter7/Image%20%282%29.png)

border-collapse属性
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter7/Image%20%283%29.png)

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter7/Image%20%284%29.png)

简单的表格布局
有用的表单元素 ：
fieldest
用来对相关信息块进行分组
为了识别每个fieldset用途，可以使用legend元素，就似fieldset的标题

表单标签：
label元素及其重要，可以帮助添加结构和增加表单的可用性和可访问下。
单击标签元素和导致相关联的表单元素获得焦点。
将标签与表单控件关联起来有两种方式
1隐式方式

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter7/Image%20%285%29.png)

2显式方式
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter7/Image%20%286%29.png)

所有表单控件都包含name属性和id属性。在表单输入控件和标签之间创建关联需要id属性，而表单数据发送回服务器需要name属性，id和name不必相同。

最好将标签光标样式改为pointer，这表明可以与标签交互

    label{
       display：block；
       cursor：pointer；
       }


文本区域尺寸可以显式地设置它们的宽度和高度。可以吧宽度设置为100%，所以宽度实际上由父元素决定。

    textarea{
    width：100%
    height：10em
    }

使用属性选择器可以寻找特定类型的表单元素，所以并不把所有输入元素都设置，而是专门寻找文本输入元素

```
input{type="text"}{
    width:20em;
}
```

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter7/Image%20%2810%29.png)

复杂的表单布局
对于比较长的复杂的表单，垂直间距会造成问题，表单也不容易查看。为了便于浏览，减少使用的垂直空间，有必要将标签和表单元素水平设置。
唯一差异是不将标签设置为块级元素，而是将标签向左浮动。

```
  label{
        float:left;
       display：block；
       cursor：pointer；
       }
```

表单标签有可能跨多行，而应该清理容器div

   

```
 form div{
        clera:left;
    }
```

在一组表单元素中，往往需要许多表单控件，但不希望显示标签，可以将标签文本设置在屏幕之外
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter7/Image%20%2813%29.png)

多列复选框
创建列效果，要将复选框分成两组，每一组放在一个div中各有一个col类，然后将这两个div元素一起放在一个具有描述性ID的fieldset中
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter7/Image%20%2814%29.png)

div设置宽度并且让它们向左浮动，从而创建出两列布局，而之前这个表单所有div在默认情况下已经被清理了，需要使用clear：none覆盖声明
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter7/Image%20%2815%29.png)

提交按钮：
通常使用一个type值设置为submit的input元素。但无法使用元素选择器选择他们，可以使用属性选择器选择。
现在逐渐流行用button元素，提供了强大的灵活性，可以使用css特性来应用样式


表单反馈
将反馈信息放在标签内，并将父元素设置为relative，反馈信息设置为absolute

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter7/Image%20%2816%29.png)
    
![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter7/Image%20%2817%29.png)
