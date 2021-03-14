# 1.2.5 数据类型

- 基本类型：number、boolean、string、undefined、null
- 引用类型：array、object、function、regexp...

**判断区别：**

- **基本类型**进行相等判断时，会比较**值**是否相等。
- **引用类型**进行相等判断时，会比较**地址**是否相等。也就是说会比较是否为内存中的同一个东西。

## 深克隆与浅克隆

- 使用arr1==arr2**不会**克隆数组
- 浅克隆：**只克隆数组的第一层**
- 深克隆：**克隆数组的所有层**，要使用递归技术。

**深克隆：**

```js
function deepClone(arr)
{
    var result=[];
    for(var i=0;i<arr.length,i++)
    {
        if(Array.isArray(arr[i]))
        {
            result.push(deepClone(arr[i]));
        }
        else
        {
            result.push(arr[i]);
        }
    }
    return result;
}
```

