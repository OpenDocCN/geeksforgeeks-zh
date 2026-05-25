# JavaScript `slice()` 方法

> 原文：[https://www.geeksforgeeks.org/javascript-array-slice-method/](https://www.geeksforgeeks.org/javascript-array-slice-method/)

下面是 `slice()` 方法的例子。

### 例：

```javascript
<script>
function func() {
    // Original Array
    var arr = [23,56,87,32,75,13];
    // Extracted array
    var new_arr = arr.slice(2,4);
    document.write(arr);
    document.write("<br>");
    document.write(new_arr);
}
func();
</script>
```

### 输出：

```text
[23,56,87,32,75,13]
[87,32]
```

`arr.slice()` 方法返回一个新数组，该数组包含实现它的数组的一部分。原文不变。

## 语法：

```javascript
arr.slice(begin, end)
```

## 参数：

该方法接受两个参数，如上所述，如下所述：

*   `begin`：该参数定义了要提取部分的起始索引。如果缺少该参数，则该方法将 `begin` 作为 `0`，因为它是默认的 `begin` 值。
*   `end`：该参数是要提取部分的索引（不包括 `end` 索引）。如果未定义该参数，则提取直到结束的数组，因为它是默认的 `end` 值。如果 `end` 值大于数组长度，则 `end` 值变为数组长度。

## 返回值：

这个方法返回一个新的数组，其中包含了原始数组的一部分。

以下示例说明了 JavaScript `slice()` 方法：

### Example 1：

In this example the `slice()` method extracts the entire array from the given string and returns it as the answer, Since no arguments were passed to it.

```javascript
var arr = [23,56,87,32,75,13];
var new_arr = arr.slice();
document.write(arr);
document.write(new_arr);
```

### 输出：

```text
[23,56,87,32,75,13]
[23,56,87,32,75,13]
```

### Example 2：

In this example the `slice()` method extracts the array starting from index `2` till the end of the array and returns it as the answer.

```javascript
var arr = [23,56,87,32,75,13];
var new_arr = arr.slice(2);
document.write(arr);
document.write(new_arr);
```

### 输出：

```text
[23,56,87,32,75,13]
[87,32,75,13]
```

### Example 3：

In this example the `slice()` method extracts the array from the given array starting from index `2` and including all the elements less than the index `4`.

```javascript
var arr = [23,56,87,32,75,13];
var new_arr = arr.slice(2,4);
document.write(arr);
document.write(new_arr);
```

### 输出：

```text
[23,56,87,32,75,13]
[87,32]
```

下面提供了上述方法的代码：

### 程序 1：

```javascript
<script>
function func() {
    //Original Array
    var arr = [23,56,87,32,75,13];
    //Extracted array
    var new_arr = arr.slice();
    document.write(arr);
    document.write("<br>");
    document.write(new_arr);
}
func();
</script>
```

### 输出：

```text
[23,56,87,32,75,13]
[23,56,87,32,75,13]
```

### 程序 2：

```javascript
<script>
function func() {
    //Original Array
    var arr = [23,56,87,32,75,13];
    //Extracted array
    var new_arr = arr.slice(2);
    document.write(arr);
    document.write("<br>");
    document.write(new_arr);
}
func();
</script>
```

### 输出：

```text
[23,56,87,32,75,13]
[87,32,75,13]
```

## 支持的浏览器：

JavaScript `slice()` 方法支持的浏览器如下：

*   谷歌 Chrome 1 以上
*   边缘 12 及以上
*   Firefox 1 及以上版本
*   Internet Explorer 4 及以上版本
*   歌剧 4 及以上
*   Safari 1 及以上