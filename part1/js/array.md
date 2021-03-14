# 1.2.4 数组

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

## 字符串与数组

数组的`join()`方法可以使数组转为字符串，字符串的`split()`方法可以使字符串转为数组。

字符串也可以使用方括号中写下标的形式访问某个字符，等价于`charAt()`方法。

## join()

`join()`的参数表是什么字符作为**连接符**，如果流控则默认以逗号分隔，如同调用`string()`方法。

## split()

`split()`的参数表示以什么字符**拆分字符串**，一般不能留空。

## concat()

`concat()`可以**合并连接**多个数组。

```javascript
var arr1=[1,2,3];
var arr2=[4,5,6];

console.log(arr1.concat(arr2));
var arr3=[7,8,9];
console.log(arr1.concat(arr3));
```
```
>[1,2,3,4,5,6]
>[1,2,3,4,5,6,7,8,9]
```

>concat方法不会改变原数组。

## reverse()

`reverse()`用来将数组中的全部项顺序**置反**

```javascript
var arr=["A","B","C"];
console.log(arr.reverse());
```
```
>["C","B","A"]
```

## sort()

数组**排序**可用`sort()`方法，**该方法的参数又是一个函数。传入参数有两个实参，分别代表数组中靠前和靠后的项，如果需要交换它们的位置，则返回任意正数，否则就返回负数。**

```javascript
arr.sort(function(a,b){
    if(a>b){
        return 1;
    }
    if(a<b){
        return -1;
    }
})//从小到大排序，=a-b,从大到小为b-a
```

## indexOf()

**`indexOf()`可搜索数组中的元素**，并返回它所在的位置，若元素不存在，则返回**-1**。

## includes()

`includes()`的功能是**判断一个数组是否包含一个指定的值**，返回布尔值。

## splice()

`splice()`用于**替换数组中的指定项**。

```javascript
var arr=['a','b','c','d','e','f','g'];
arr.splice(3,2,'x','y','x');//从下标为3的项开始，连续替换2项
console.log(arr);
```

```
>['a','b','c','x','y','z','f','g']
```

`splice()`用于在指定位置**插入新项**（第二个参数设置为0即可）。

```javascript
var arr=['a','b','c','d'];
arr.splice(3,0,'x','y','x');
console.log(arr);
```

```
>['a','b','c','x','y','z','d']
```

`splice()`可用于**删除指定项**（不设置替换新项即可）

```js
var arr=['a','b','c','d','e','f','g'];
arr.splice(2,4);//从下标为3的项开始，连续替换2项
console.log(arr);
```

```
>['a','b','g']
```

## slice()

`slice()`用于**得到子数组**，类似于字符串的`slice()`方法。

- `slice(a,b)`截取的子数组从下标为a项开始到下标为b（但不包括b）结束。
- `slice()`如果不提供第二个参数，则表示从指定项开始，提取所有后续项作为子数组。
- `slice()`的参数允许为负数，表示数组的倒数几项。

```js
var arr=['a','b','c','d','e','f'];
console.log(arr.slice(2,5));
console.log(arr.slice(2));
console.log(arr.slice(2,-1));
```

```
>['c','d','e']
>['c','d','e','f']
>['c','d','e']
```