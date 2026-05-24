# D3.js | `d3.merge()`功能

> 原文: [https://www.geeksforgeeks.org/d3-js-d3-merge-function/](https://www.geeksforgeeks.org/d3-js-d3-merge-function/)

D3.js 中的 `d3.merge()`函数用于将两个给定的数组合并成一个数组。

## 语法:

```
d3.merge(Array1, Array2)
```

## 参数:

该功能接受上面提到的和下面描述的两个参数:

*   `Array1`: 这是第一个元素将与 `Array2` 合并的数组。
*   `Array2`: 这是第二个数组，其元素将与 `Array1` 合并。

## 返回值:

返回合并后的单个数组。

以下程序说明了 D3.js 中的 `d3.merge()`功能。

### 示例 1:

```
<html>

<head>
    <title>Getting a single array after 
      merging of the two given array</title>
</head>

<body>
    <script src='https://d3js.org/d3.v4.min.js'>
  </script>

<script>
        // initialising the arrays of elements
        var Array1 = [10, 20, 30];
        var Array2 = [1, 2, 3];

// Calling to d3.merge() function
        A = d3.merge([
            [Array1],
            [Array2]
        ]);

// Getting a single array after 
        // merging of the two given array
        document.write(A + "<br>");
    </script>
</body>

</html>
```

**输出:**

```
[10, 20, 30, 1, 2, 3]
```

### 示例 2:

```
<html>

<head>
    <title>
      Getting a single array after
      merging of the two given array
  </title>
</head>

<body>
    <script src='https://d3js.org/d3.v4.min.js'>
  </script>

<script>
        // initialising the arrays of elements
        var Array1 = ["A", "B", "C"];
        var Array2 = ["a", "b", "c"];

// Calling to d3.merge() function
        A = d3.merge([
            [Array1],
            [Array2]
        ]);

// Getting a single array 
        // after merging of the two given array
        document.write(A + "<br>");
    </script>
</body>

</html>
```

**输出:**

```
[A, B, C, a, b, c]
```

**参考:** [https://devdocs.io/d3~4/d3-array#merge](https://devdocs.io/d3~4/d3-array#merge)