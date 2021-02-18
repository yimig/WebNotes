# 1.1.3 文字样式属性

## font-weight

设置字体**粗细**，通常位`normal`(改h系列标签加粗的特性)或`bold`。

### 常用值

- 数值
- normal    与400等值
- bold      与700等值

## font-style

设置字体**倾斜**，可以消除`i`、`em`等标签的倾斜效果。

### 常用值

-   normal  不倾斜/消除`i`、`em`等标签的倾斜效果
-   italic  倾斜

## text-decoration

设置字体的**修饰线外观**。

### 常用值

-   none 消除/无修饰线
-   underline 下划线
-   line-through    删除线

## font-family

设置**字体**。
可列多项为后备字体，一般英文字体放前面。

**必须是用户电脑中已安装好的字体，否则自定义字体让用户在加载时下载**。有字体后通过`@font-face`定义，用法现查。

```css
font-family:"微软雅黑";
font-family:"Times New Roman",Georgia,Serif;
```

## text-indent

设置首行文本**缩进量**。
单位是em，即一个字符的长度。

## line-height

自定义**行高**（行间距），可写px为单位，也可以写倍数或者百分数。

### 单行文本设置垂直居中

1. 设置行高=盒子高度
2. 设置`text-align:center`即可实现文本水平居中

## font合写

|合写公式|示例|
|-|-|
|font:字号/行高 字体|font:20px/1.5 Arial,"微软雅黑"|
|font:倾斜 加粗 字号/行高 字体|font:italic bold 20px/1.5 Arial,"微软雅黑"|

## 继承性

文本相关的属性普遍有继承性，如：
1. color
2. font-开头的属性
3. list-开头的属性
4. text-开头的属性
5. line-开头的属性

>**就近原则**：在继承下选择器**权重计算是失效的**，采用就近原则，即：**直接选中>继承，近代继承>远代继承**。
