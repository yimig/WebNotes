# 1.1.8 变形transform

## 旋转变形

将transform属性的值设为`rotate()`即可实现旋转变形。

```
transform:rotate(旋转角度);
transform:rotate(45deg);
```

>若角度为正，则顺时针旋转，角度为负则逆时针方向旋转。

## 变形起源transform-origin

设置**变化的中心位置**。参数为以元素**左上角为中心**。

```
transform-origin:横向 纵向;
transform-origin:0 100%;
（变形起源为左下）
```

## 3D旋转

将transform属性的值设置为`rotateX()`或`rotateY()`即可实现绕横轴、纵轴旋转。

```
transform:rotateX(30deg)//向后仰
transform:rotateY(30deg)//右侧向前倾
```

### perspective属性

表示**透视强度**，可以理解为“人眼到舞台的距离”，单位为px。

```
<div>←舞台，必须设置perspective属性
    <p></p>←演员，设置transform属性
</div>
```

### 空间移动

当元素进行了3D旋转后，可继续添加`translateX()`/`translateY()`/`translateZ()`属性让元素在空间上进行移动。

```
transform:translateX(30deg) translateY(30px) translateZ(100px)
```

**注意！**

这里的X、Y、Z轴**方向**为**旋转后的坐标轴**。

## 缩放变形

将transform的值设为`scale()`即可实现缩放变形。

```
transform:scale(3);
```

>值没有单位，表示缩放倍数，当值小于1是表示缩小元素，大于1是表示放大元素。

## 斜切变形

将transform的属性的值设置为`skew()` ，即可实现斜切变形。

```
transform:skew(x斜切角度,y斜切角度)
transform:skew(10deg,20deg)
```

>效果类似侧向拉伸/扭曲

## 位移变形

将transform属性的值设置为`translate()`，即可实现位移变形。

```
transform:translate(向右移动,向左移动)
transform:translate(100px,200px)
```
>实现效果与**相对定位**非常像，位移变形也会“老家留坑”、“形影分离”。

