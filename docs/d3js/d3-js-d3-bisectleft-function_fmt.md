# D3.js 中的 d3.bisectLeft() 函数

> 原文: [https://www.geeksforgeeks.org/d3-js-d3-bisectleft-function/](https://www.geeksforgeeks.org/d3-js-d3-bisectleft-function/)

`d3.bisectLeft()` 函数是 D3.js 中的内置函数，它接受一个值作为其参数之一，并返回索引以将元素插入作为另一个参数传递的数组中，从而在指定范围或整个数组中保持排序顺序。

默认情况下，函数在查找索引时会考虑整个数组，除非通过将开始和结束作为参数传递给函数来指定范围。

函数进行二分搜索以查找该值，并检查该值是否已经存在于该范围内。如果找到，它将被插入到该元素的左侧。

## 语法

```javascript
d3.bisectLeft(array, value, start, end)
```

## 参数

这个函数接受四个参数：

*   `array`：此*必需参数*包含一个元素数组。
*   `value`：这也是一个*必需参数*，包含要插入数组的值。
*   `start`：这是一个*可选参数*，指定范围的起始索引。
*   `end`：这是一个*可选参数*，指定范围的结束索引。

## 返回值

该函数返回一个整数值，表示需要在数组中插入 `value` 以保持排序顺序的索引。

## 示例

以下程序说明了 `d3.bisectLeft()` 函数的使用：

### 示例 1

该程序仅使用两个必需参数说明了 `d3.bisectLeft()` 的用法。

```html
<!DOCTYPE html>
<html>

<head>
    <title>D3 d3.bisectLeft() Function</title>
    <script src='https://d3js.org/d3.v4.min.js'></script>
</head>

<body>
    <script>
        var array = [42, 43, 53, 61, 71, 87, 91];
        var value1 = 63;
        var pos = d3.bisectLeft(array, value1);
        document.write(value1 + " needs to be inserted at " + pos + "<br>");

        var value2 = 80;
        var pos2 = d3.bisectLeft(array, value2);
        document.write(value2 + " needs to be inserted at " + pos2);
    </script>
</body>

</html>
```

**输出：**

```
63 needs to be inserted at 4
80 needs to be inserted at 5
```

### 示例 2

这个程序演示了将所有四个参数传递给 `d3.bisectLeft()` 函数的用法。

```html
<!DOCTYPE html>
<html>

<head>
    <title>D3 d3.bisectLeft() Function</title>
    <script src='https://d3js.org/d3.v4.min.js'></script>
</head>

<body>
    <script>
        var array = [42, 34, 27, 53, 61, 71, 33, 51, 87, 91];
        var value1 = 63;
        var pos = d3.bisectLeft(array, value1, 2, 5);
        document.write(value1 + " needs to be inserted at " + pos + "<br>");

        var pos2 = d3.bisectLeft(array, value1, 6, 9);
        document.write(value1 + " needs to be inserted at " + pos2);
    </script>
</body>

</html>
```

**输出：**

```
63 needs to be inserted at 5
63 needs to be inserted at 8
```

## 参考

[https://devdocs.io/d3~5/d3-array#bisectLeft](https://devdocs.io/d3~5/d3-array#bisectLeft)