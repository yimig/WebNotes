# 1.1.1 选择器和伪类

## 复合选择器

|选择器|符号|例子|解释|备注|
|-|-|-|-|-|
|后代选择器|（空格）|.box .spec|选择名为box的标签内部的类名位spec的标签|可隔代选择|
|交集选择器|无|li.spec|选择既是li标签也属于spec类的标签||
|并集选择器|,|ul,ol|选择所有ul和ol标签||

## 元素关系选择器

|选择器|符号|举例|解释|
|-|-|-|-|
|子选择器|>|div>p|选择div的严格子标签p|
|相邻兄弟选择器|+|img+p|选择img后紧接着的p标签|
|通用兄弟选择器|~|p~span|选择p元素**之后**的所有同级span元素|

## 序号选择器

选择多个同类型元素的某个或多个。**使用序号选择器时通常与后代选择器搭配使用**，如`div p:first-child`。

```html
<div>
    <p>Text1</p>
    <p>Text2</p>
    <h3>Header1</h3>
    <h3>Header2</h3>
    <p>Text3</p>
    <p>Text4</p>
    <p>Text5</p>
</div>
```

|关键字|解释|举例|效果|支持|
|-|-|-|-|-|
|:first-child|选择第一个子元素|div p:first-child|选择Text1|IE7|
|:last-child|选择最后一个元素|div p:last-child|选择Text5|IE9|
|:nth-child()|选择某个顺序位置的元素|div p:nth-child(3)|没有元素被选中，因为div的第三个子元素是h3类型。|IE9|
|:nth-of-type()|选择某个类型顺序特定位置的元素|div p:nth-of-type(3)|选择Text3|IE9|
|:nth-last-child()|选择某个倒序位置的元素|div p:nth-last-child(4)|没有元素被选中，因为div的倒数第四个子元素是h3类型。|IE9|
|:nth-last-of-type()|选择某个类型倒序特定位置的元素|div p:nth-last-of-type(4)|选择Text2|IE9|

>:nth-child()的括号中可写成**an+b**的形式，**表示从b开始每a个选择一个**，不能写成b+an。

如：`div p:nth-child(3n+2)`表示div中从第二个元素开始每3个元素选择一个p元素。在上例中选择**Text2、Text3**。

## 属性选择器

|关键字（方括号中的）|举例|解释|
|-|-|-|
|无|img[alt]|选择有alt属性的img|
|=|img[alt="xxx"]|选择alt属性是xxx的img|
|^=|img[alt^="xxx"]|选择alt属性以xxx开头的img|
|\$=|img[alt\$="xxx"]|选择alt属性以xxx结尾的img|
|~=|img[alt~="xxx"]|选择alt属性空格隔开有xxx字样的img|
|\|=|img[alt\|="xxx"]|选择alt属性以“xxx-”开头的img|
|\*=|img[alt\*="xxx"]|选择alt属性含有xxx的img|


## 伪类

伪类是添加到选择器的描述性词语，指定要选择的元素的**特殊状态**。

**a标签**有以下四种特殊状态：

|伪类|解释|
|-|-|
|a:link|没有被访问时的链接|
|a:visited|已被访问过的链接|
|a:hover|正被鼠标悬停的链接|
|a:active|正被激活的链接（按下但还没松开）|

## CSS3伪类

|伪类|解释|备注|
|-|-|-|
|:empty|选择空标签|内部不包含任何元素/文字，空格也不行|
|:focus|选择当前获得焦点的**表单元素**||
|:enabled|选择当前有效的**表单元素**||
|:disabled|选择当前无效的**表单元素**||
|:checked|选择当前已勾选的**单选按钮**或**复选框**||
|:root|选择根元素，即\<html\>标签|该伪类前不需加任何元素|

## 伪元素

表示虚拟动态创建的元素，一般规定用**双冒号**表示，IE8以上也可以用单冒号。

具体用法参见[文档](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Pseudo-elements)