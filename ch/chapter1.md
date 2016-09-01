#第一章：基础知识
## 设计代码的结构
##1.1.1标记简史
早期的web仅仅是一系列相互连接的研究文档，使用HTML添加基本的格式和结构。而表格仅仅是web网页布局的工具，而不是数据显示，这样的缺点是使代码变得越来越难以理解和维护，代码的复杂性进一步地提高，且布局及其脆弱，很容易被破坏。随后有人使用透明的gif来控制表格的大小，然而HTMl这种简单的标记语言反而复杂，混乱和容易出错。因此随着css的出现，可以很好地跟HTML分离，提高代码的可维护性。
### 1.意义的重要性

有意义的页面更容易处理
程序和其他设备也可以理解有意义的标记
更重要的是，可以很简便地调整你所需要的样式。

### 2.ID和类名
id用于标识页面上的特定元素，必须是唯一的。
类名，比id有这更强大的功能，在同一个页面，可以用多个相同的类名。

### 3.为元素命名
在分配ID和类名时，尽可能地保持名称与表现方式无关，应该根据它们所具有的特征来为元素命名。

### 4.ID和类
一般原则是，类应该应用于概念相似的元素，这些元素可以出现在同一页面上的位置，而id必须确保页面上的元素非常独特而且只使用一次。类名具有灵活性，但也要避免过度地使用。

### 5.div和span
div可以为页面提供布局区分的特征，但也避免过度使用，是代码尽可能地简洁和有意义。

### 6微格式
由于HTML中缺少相应的元素，好难突出显示人，地点或日期类型的信息，有一组开发人员决定开发一套标准的命名约定和标记模式来表示数据。基于vCard和iCalendar等现有的数据格式，称为微格式。

### 7.不同版本的HTMl 和CSS

## 1.1.2 文档类型，DOCTYPE切换和浏览器模式
DTD（文档类型定义）是一组及其刻度的规则，它们定义XML或HTML的特定版本中允许有什么，不允许有什么。浏览器通过分析压面的DOCTYPE声明来了解使用哪个DTD。

DOCTYPE声明是指HTML文档开头处的一行或两行代码，它描述使用哪个DTD。

##  1.1.3有效验证性

使用W3C验证器

#### 1.浏览器模式
- 标准模式 严谨
- 混杂模式 宽松

#### 2.DOCTYPE 切换
