# JavaScript 数组 `shift()` 方法

> 原文：[https://www.geeksforgeeks.org/javascript-array-shift-method/](https://www.geeksforgeeks.org/javascript-array-shift-method/)

下面是 `Array.shift()` 方法的例子。

## 示例

```html
<script>
function func() {
    // Original array
    var array = ["GFG", "Geeks", "for", "Geeks"];

    // Checking for condition in array
    var value = array.shift();

    document.write(value);
    document.write("<br />");
    document.write(array);
}

func();
</script>
```

**输出：**

```
GFG
Geeks, for, Geeks
```

`arr.shift()` 方法移除数组的第一个元素，从而通过 `1` 减小原始数组的大小。

## 语法

```
arr.shift()
```

## 参数

此方法不接受任何参数。

## 返回值

这个函数返回数组中被移除的第一个元素。如果数组为空，则该函数返回 `undefined`。

## 注意

这个函数也可以和其他行为类似数组的 JavaScript 对象一起使用。

## 示例说明

以下示例说明了 JavaScript 数组 `shift()` 方法：

### 示例 1

在这个示例中，`shift()` 方法移除了数组的第一个元素，因此它返回 `34`。

```javascript
var arr = [2, 5, 8, 1, 4];
var value = arr.shift();
document.write(value);
document.write(arr);
```

输出：

```
2
5,8,1,4
```

### 示例 2

在这个示例中，`shift()` 方法尝试移除数组的第一个元素，但数组是空的，因此它返回 `undefined`。

```javascript
var arr = [];
var value = arr.shift();
document.write(value);
document.write(arr);
```

**输出：**

```
undefined
```

## 完整代码

### 程序 1

```html
<script>
function func() {
    // Original array
    var array = [34, 234, 567, 4];

    // Checking for condition in array
    var value = array.shift();

    document.write(value);
    document.write("<br />");
    document.write(array);
}

func();
</script>
```

**输出：**

```
34
234,567,4
```

### 程序 2

```html
<script>
function func() {
    // Original array
    var array = [];

    // Checking for condition in array
    var value = array.shift();

    document.write(value);
    document.write("<br />");
    document.write(array);
}

func();
</script>
```

**输出：**

```
undefined
```

## 支持的浏览器

JavaScript `Array.shift()` 方法支持的浏览器如下：

*   Google Chrome 1 及以上版本
*   Edge 12 及以上
*   Firefox 1 及以上版本
*   Internet Explorer 5.5 及以上版本
*   Opera 4 及以上
*   Safari 1 及以上