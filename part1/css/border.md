# 边框border属性

## border三要素

```
border: 线宽度 线形 线颜色;
border: 1px solid red;
```
|线形|值|
|-|-|
|实线|solid|
|虚线|dashed|
|点状线|dotted|

### 分写四个方向的边框

```
border-top:1px solid red;
    -right:...;
    -left:...;
    -bottom:...;
```

>border-left:none;去掉左边框，以此类推。

### 分开写的小属性

```
border-top-width:宽度
border-top-style:线形
border-top-color:颜色
```

>颜色：transparent 透明色

### 做等腰三角形

**盒子宽高都是0，只有一条边框有颜色，其他边框为透明色。**

## 圆角 border-radious

值通常为px单位，表示圆角半径。

```
border-radius:10px;
```

也可以使用**百分比**作为单位，表示圆角起始于每条边的哪里。

```
border-radius:20%;
```

### 做正圆形

- border-radius为**盒子长/宽的一半**。
- `border-radius:50%`，正方形盒子是正圆，长方形是椭圆。

### 单独设置圆角

```
border-radius:左上 右上 右下 左下
border-radius:10px 20px 30px 40px;
```

>小属性：border-top-left-radius 左上角。

>小属性的用处为**层叠大属性**