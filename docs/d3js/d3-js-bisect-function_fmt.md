# D3.js `bisect()` 函数

> 原文: [https://www.geeksforgeeks.org/d3-js-bisect-function/](https://www.geeksforgeeks.org/d3-js-bisect-function/)

`bisect()` 函数是 D3.js 中的内置函数，它接受一个值作为其参数之一，并返回索引，将元素插入作为另一个参数传递的数组中，以保持指定范围或整个数组中的排序顺序。

默认情况下，函数在查找索引时会考虑整个数组，除非通过将开始和结束作为参数传递给函数来指定范围。

函数二进制搜索值，并检查该值是否已经存在于该范围内。如果找到，它将被插入到该元素的左侧。

## 语法

```
d3.bisect(array, value, start, end)
```

## 参数

这个函数接受上面提到的和下面描述的四个参数：

*   `array`: 这是必需的参数，包含一个元素数组。
*   `value`: 这也是必需的参数，包含要插入到数组中的值。
*   `start`: 这是一个可选参数，指定范围的起始索引。
*   `end`: 这是一个可选参数，指定范围的最后一个索引。

## 返回值

该函数返回一个整数值，表示数组中需要插入值以保持排序顺序的索引。

## 示例

以下程序说明了 `d3.bisect()` 函数的使用：

### 示例 1

该程序说明了仅通过两个必需参数的 `d3.bisect()` 的用法。

```
<!DOCTYPE html>
<html>
<head>
    <title>D3.js d3.bisect() Function</title>
    <script src='https://d3js.org/d3.v4.min.js'></script>
</head>
<body>
    <script>
        var array = [42, 43, 53, 61, 71, 87, 91];
        var value1 = 63;
        var pos = d3.bisect(array, value1);
        document.write(value1 + " needs to be inserted at " + pos + "<br>");

        var value2 = 80;
        var pos2 = d3.bisect(array, value2);
        document.write(value2 + " needs to be inserted at " + pos2);
    </script>
</body>
</html>
```

**输出:**

```
63 needs to be inserted at 4
80 needs to be inserted at 5
```

### 示例 2

这个程序演示了 `d3.bisect()` 将所有四个参数传递给函数的用法。

```
<!DOCTYPE html>
<html>
<head>
    <title>D3.js d3.bisect() Function</title>
    <script src='https://d3js.org/d3.v4.min.js'></script>
</head>
<body>
    <script>
        var array = [42, 34, 27, 53, 61, 71, 33, 51, 87, 91];
        var value1 = 63;
        var pos = d3.bisect(array, value1, 2, 5);
        document.write(value1 + " needs to be inserted at " + pos + "<br>");

        var pos2 = d3.bisect(array, value1, 6, 9);
        document.write(value1 + " needs to be inserted at " + pos2);
    </script>
</body>
</html>
```

**输出:**

```
63 needs to be inserted at 5
63 needs to be inserted at 8
```

## 参考

[https://devdocs.io/d3~5/d3-array#bisect](https://devdocs.io/d3~5/d3-array#bisect)