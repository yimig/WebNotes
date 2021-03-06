# 1.2.2 变量

## 定义变量

```javascript
var a=5; //声明并赋值
```

- 变量名只能由**字母、数字、下划线、$**组成，不能以数字开头，且不能是关键字或保留字。变量名**大小写敏感**。
- 变量名用**Camel**命名法，或者**_**连接。
- 只定义不赋值的变量值为`undefined`。
- 不用var定义直接赋值的变量会产生作用域问题，即定义为**全局问题**。

## 变量声明提升

可以**提前使用一个稍后才声明的变量**，而不会引发异常。

原理：在执行所有代码前，JS有预解析阶段，会**预读**所有变量。

```javascript
console.log(a);
var a=12;//只提升定义，不提升值
```
>out: undefined

等价于

```javascript
var a;
console.log(a);
a=12;
```

**注意：**

- 变量声明是JS特性，所以经常出面试题
- 实际开发时不要刻意使用变量声明提升


