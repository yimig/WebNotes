# 数组

## 定义数组

```javascript
var arr=['A','B','C'];
var arr=new Array('A','B','C');
var arr=new Array(4)//长度为4，值为undefined的数组
```
>访问不存在的项会返回undefined。

## 数组类型

- 数组用`typeof()`检测结果为`object`
- 可用`Array.isArray()`来检测对象是否为数组
- 后面的课程将介绍用“鸭式变形”检测方法

## 更改数组项

若更改数组项越界，则会创建该项，但中间的项值为`undefined`。

**数组的头尾操作**

方法|功能
-|-
push()|在尾部插入新项
pop()|在尾部删除
unshift()|在头部插入新项
shift()|在头部删除

>pop()/shift()方法不仅会删除数组末项，而且还会返回被删除的项。

