# JavaScript 数组 `copyWithin()` 方法

> 原文：[https://www.geeksforgeeks.org/javascript-array-copywithin-method/](https://www.geeksforgeeks.org/javascript-array-copywithin-method/)

下面是数组 `copyWithin()` 方法的例子。

### 示例

```javascript
<script>
    // Input array
    var array = [1, 2, 3, 4, 5, 6, 7];

    // placing at index position 0 the element
    // between index 3 and 6
    document.write("Array " + array.copyWithin(0, 3, 6));
</script>
```

**输出：**

```
Array 4, 5, 6, 4, 5, 6, 7
```

`arr.copyWithin()` 方法将数组的一部分复制到同一个数组中并返回，而不修改其大小，即复制同一个数组中的数组元素。

### 语法

```
array.copyWithin(target, start, end)
```

### 参数

该方法接受三个参数，如下所述：

*   **target**：要复制到的目标索引位置（必需）。
*   **start**：可选。开始复制元素的索引位置（默认值为 0）。
*   **end**：可选。停止复制元素的索引位置（默认值为 `array.length`）。

### 返回值

返回修改后的数组。

上述方法的更多示例代码如下：

### 程序一

```javascript
<script>
    // Input array
    var array = [1, 2, 3, 4, 5, 6, 7];

    // Placing from index position 0 the
    // Element from index 4
    document.write("Array " + array.copyWithin(0, 4));
</script>
```

**输出：**

```
Array 5, 6, 7, 4, 5, 6, 7
```

### 程序二

```javascript
<script>
    // Input array
    var array = [1, 2, 3, 4, 5, 6, 7];

    // Placing from index position 3
    // The element from index 0
    document.write("Array " + array.copyWithin(3));
</script>
```

**输出：**

```
Array 1, 2, 3, 1, 2, 3, 4
```

### 应用

每当我们需要将任何数组的内容复制到同一个数组时，我们都会在 JavaScript 中使用 `arr.copyWithin()` 元素。

```javascript
<script>
    // Input array
    var array = [1, 2, 3, 4, 5, 6, 7];

    // Placing at index position 0 the
    // Element between index 4 and 5
    document.write("Array " + array.copyWithin(0, 4, 5));
</script>
```

**输出：**

```
Array 5, 2, 3, 4, 5, 6, 7
```

### 支持的浏览器

JavaScript 数组 `copyWithin()` 方法支持的浏览器如下：

*   Microsoft Edge 12.0
*   Mozilla Firefox 32.0
*   Opera 32.0
*   Safari 9