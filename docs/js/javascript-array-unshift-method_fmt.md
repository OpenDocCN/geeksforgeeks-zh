# JavaScript 数组 `unshift()` 方法

> 原文: [https://www.geeksforgeeks.org/javascript-array-unshift-method/](https://www.geeksforgeeks.org/javascript-array-unshift-method/)

下面是数组 `unshift()` 方法的例子。

**例:**

```html
<script>
function func() {
    // Original array
    var array = ["GFG", "Geeks", "for", "Geeks"];

    // Checking for condition in array
    var value = array.unshift("GeeksforGeeks");

    document.write(value);
    document.write("<br />");
    document.write(array);
}
func();
</script>
```

**输出:**

```
GeeksforGeeks,GFG,Geeks,for,Geeks
```

`arr.unshift()` 方法用于向给定数组的开头添加一个或多个元素。该函数通过增加数组中的元素数量来增加现有数组的长度。

## 语法

```
array.unshift(element1, element2, ..., elementX)
```

## 参数

此方法接受单个参数。

*   **element**: 这个参数需要在数组的开头添加元素。

## 返回值

该函数在数组的开头插入参数后，返回数组的新长度。

以下示例说明了 JavaScript 数组 `unshift()` 方法:

### 示例 1

在此示例中，函数 `unshift()` 将 28 和 65 添加到数组的开头。

```javascript
var arr = [23,76,19,94];
document.write(arr.unshift(28,65));
document.write(arr);
```

**输出:**

```
28,65,23,76,19,94
```

### 示例 2

在此示例中，`shift()` 方法尝试移除数组的第一个元素，但数组为空，因此它返回 `undefined`。

```javascript
var arr = [23,76,19,94];
document.write(arr.unshift());
document.write(arr);
```

**输出:**

```
23,76,19,94
```

上述方法的代码如下:

### 程序 1

```html
// JavaScript to illustrate unshift() function
<script>
function sayHello() {
    var arr = [23,76,19,94];

    // Adding elements to the front of the array
    document.write(arr.unshift(28,65));
    document.write("<br>");
    document.write(arr);
}
sayHello();
</script>
```

**输出:**

```
28,65,23,76,19,94
```

### 程序 2

```html
// JavaScript to illustrate unshift() function
<script>
function sayHello() {
    var arr = [23,76,19,94];

    // Adding elements to the front of the array
    document.write(arr.unshift(28,65));
    document.write("<br>");
    document.write(arr);
}
sayHello();
</script>
```

**输出:**

```
23,76,19,94
```

## 支持的浏览器

JavaScript 数组 `unshift()` 方法支持的浏览器如下:

*   谷歌 Chrome 1 及以上版本
*   边缘 12 及以上
*   Firefox 1 及以上版本
*   Internet Explorer 5.5 及以上版本
*   歌剧 4 及以上
*   Safari 1 及以上