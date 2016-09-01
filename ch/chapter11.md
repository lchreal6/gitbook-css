# 第十一章： 实例研究 ：Climb the Mountains

样式表中的组织和约定：
开发了一套基本的规则和约定，作为编写HTML，CSS，JavaScript和ExpressionEngine的起点。它规定了链接的CSS文件，命名约定，模块，插件和库脚本，确保由任意团队成员领导或参与的任何项目都坚持统一的约定，让任何人在任何时候更容易参加项目的开发。

scree.css和reset.css
sereen.css
内容说明，对网页的样式表采用描述性的说明，使得开发者能够明晰地了解各个结构具体应用的样式，方便参与进来。

```
/*

    CLIMB THE MOUNTAINS by ERSKINE DESIGN
    VERSION 1.0

    CONTENTS ----------

           1.BODY
           2.DEFAULT STYLING
           3.HEADINGS
           4.LINKS
           5.IMAGES
           6.LAYOUT
           7.BRANDING/MASTHEAD
           8.NAVIGATION
        9.SITEINFO/FOOTER
        10.GLOBAL ELEMENTS
            10.1 CAPTIONED IMAGE
            10.2 ELEVATION
            10.3 DISTANCE/ELEVATION PARAGRAPH
        11.HOMEPAGE
            11.1 CONTENT PRIMARY
            11.2 CONTENT SECONDARY
            11.3 CONTENT TERTIARY

    -------------------

    COLOURS -----------

        blue #278dab
        green #339900   

    -------------------
```


reset
清除默认样式，定义样式。
使用条件注释的IE样式表

![](http://ocjqhfs9p.bkt.clouddn.com/img/chapter11/Image.png)

使用body类控制导航

突出显示当前页面
通过body类来控制选择器，特定地设置样式


战略性地选择元素
深层后代选择器


firest-child
:first-child伪类只选择包含元素的第一个子元素。

相邻同胞选择器：
可以选择无序列表中的第四个子元素列表，可以这样写
div ul li+li+li+li{

}

RGBa , 组合类，border-radius,box-shadow.




