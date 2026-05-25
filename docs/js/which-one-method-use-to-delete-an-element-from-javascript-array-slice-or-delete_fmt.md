# 用哪一种方法从 JavaScript 数组中删除一个元素（切片还是删除）？

> 原文：[https://www.geeksforgeeks.org/which-one-method-use-to-delete-an-element-from-javascript-array-slice-or-delete/](https://www.geeksforgeeks.org/which-one-method-use-to-delete-an-element-from-javascript-array-slice-or-delete/)

我们可以使用这两种方法从 JavaScript 数组中删除一个元素。答案完全取决于应用程序和程序员。

## `slice()` 方法做什么？

顾名思义，`slice` 方法对数组进行切片，并返回新数组的副本。这个方法不影响主数组，它只是返回数组的副本。我们可以将数组的这个副本给主数组或任何其他数组，以获得切片数组。

### 语法

```
array.slice(arg1, arg2);
```

### 参数

它接受以下两个参数：

*   `arg1`：它指的是方法开始切片的起始索引。起始索引是包含的，这意味着如果我们给 0，它将从第 0 个索引开始。
*   `arg2`：指的是结束索引。结束索引是不包含的，这意味着它将不包括结束索引处的元素。

没有必要给出两个参数，如果我们不提供开始索引，它将从第 0 个索引开始，如果我们不提供结束索引，它将到达最后一个索引。

### 返回值

返回新数组的副本。

### 示例 1

这里，我们给出的起始索引为 2，结束索引为 4，因此它将对元素 2、3 进行切片。如您所见，它返回新数组的副本，我们将它存储在同一个数组中。该方法还缩短了数组长度。以前数组的长度是 4，对数组进行切片后，它变成了 2。

```javascript
<script>
    // Sample array
    var arr = ["super", "duper", "upar", "chopper"];

    // Printing array length before function call
    console.log(arr.length);

    // Function call
    arr = arr.slice(2, 4);

    // Printing array and its length after function call
    console.log(arr, arr.length);
</script>
```

**输出**

```
[ 'upar', 'chopper' ] 2
```

### 示例 2

这里我们没有给出结束索引，所以它将从第一个索引开始，切片到最后一个。

```javascript
<script>
    // Sample array
    var arr = ["super", "duper", "upar", "chopper"];

    // Printing length before function call
    console.log(arr.length);

    // Function call
    arr = arr.slice(1);

    // Printing array and its length after function call
    console.log(arr, arr.length);
</script>
```