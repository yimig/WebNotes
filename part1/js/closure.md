## 1.2.7 闭包

闭包(Closure)是**函数本身和该函数生命是所处环境状态的组合**。

即函数能“记忆住”其定义时所处的环境，**即使函数不在其定义的环境中被调用，也能访问定义时所处的环境变量**。

JS每次创建函数时都会创建闭包。但是，闭包特性往往需要将函数“换一个地方”执行才能被观察出来。

> 闭包很有用，因为**它允许我们将数据与操作该数据的函数关联起来**。这与“面向对象编程”有少许相似之处。

**功能：**

- 记忆性
- 模拟私有变量

## 记忆性

当闭包产生时，函数所处的环境状态**会始终保持在内存中，不会在外层函数调用后被自动清除**。这就是闭包的记忆性。

### 利用记忆性制作函数的“工厂函数”

要求制作函数`checkTemp()`检查输入的温度是否正常，但是温度标准有很多种：

```js
function createCheckTemp(standardTemp)
{
    function checkTemp(n){
        if(n<=standardTemp)alert("温度过高！");
        else alert("温度正常。");
    }
    return checkTemp;
}

//针对不同标准的温度测量
var checkTemp_human=createCheckTemp(37.2);//测量人的体温
var checkTemp_mechine=createCheckTemp(100.0);//测量机器的工作温度
```

## 模拟私有变量

```js
//某对象工厂方法
function func()
{
    var a=0;//定义局部变量a
    return{
        getA:function()
        {
            return a;
        }
    };
}

var obj=func();
//如果想在func函数外使用a，唯一方法就是调用getA()方法
console.log(obj.getA());
```

> 注意：**不能滥用闭包**，否则会造成网页的性能问题，严重时可能导致**内存泄漏**。所谓内存泄漏指的是程序中已动态分配的内存由于某种原因未释放或无法释放。
