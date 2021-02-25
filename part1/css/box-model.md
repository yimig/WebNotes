# 1.1.4 盒模型

**width、height**是**内容**的宽高。

**总宽=width+左右padding+左右border**

## border

|border: 宽度 类型 颜色;|border:10px solid red;|
|-|-|

详细内容参见[边框border属性](border.md)

## padding

赋值顺序为**上右下左** 即从上开始的顺时针赋值。

### 合写原则

每个||中填入宽度：

padding:|上|  |右|  |下|  |左|

padding:|上| |左右| |下|  ~~|左|~~

padding:|上下|   |左右|

padding:|上下左右|

## margin

用法类似`padding`。

### 竖直方向塌陷

**竖直方向上的小margin会塌陷到大margin中**，以较大值为准。

```
    ▕▔▔▔▔▔▏
      ▔▔▔▔▔      ▔ 
  30px ↓    ↑ 40px   │  total:40px
            │        │
    ▕▔▔▔▔▔▏    ▔
      ▔▔▔▔▔
```

>**有的元素默认有margin**，比如body、ul、p等，开始时需进行清除。

```css
/*清除margin和padding*/
*{
    margin:0;
    padding:0;
}
```

## 盒子的水平居中

左右设为auto。即`margin:0 auto`。

垂直居中用**绝对定位**。

## box-sizing

给盒子添加`box-sizing:border-box`后，合资的width、height数字就表示为实际占有的宽高（不含margin），即**padding、border不再“外扩”而是“内缩”**，常用于移动网页开发。