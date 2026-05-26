# Array.shift()方法

> 原文：[https://www.geeksforgeeks.org/typescript-array-shift-method/](https://www.geeksforgeeks.org/typescript-array-shift-method/)

``Array.shift()`` 是一个内置的 TypeScript 函数，用于从数组中移除第一个元素并返回该元素。

## 语法

```
array.shift(); 
```

## 参数

该方法不接受任何参数。

## 返回值

此方法返回数组移除的单个值。

## 示例

以下示例说明了 TypeScriptJS 中的 ``数组移位()方法``：

### 例 1：JavaScript

```
<script>
   // Driver code
    var arr = [ 11, 89, 23, 7, 98 ];

    // use of shift() method 
    var val = arr.shift();

    // printing
    console.log( val );
    console.log( arr );
</script>
```