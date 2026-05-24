# d3.quantile() 函数

> 原文：`https://www.geeksforgeeks.org/d3-js-d3-quantile-function/`

D3.js 中的 `d3.quantile()` 函数用于返回给定排序元素数组的 p 分位数。其中 p 是位于 [0, 1] 范围内的数字。

## 语法

```
d3.quantile(Array, p)
```

## 参数

这个函数接受上面提到的和下面描述的两个参数：

*   `Array`：它保存一个有序的元素数组。
*   `p`：是在给定的排序元素数组上返回的 p 分位数。

## 返回值

返回给定排序元素数组的 p 分位数。

下面的程序说明了 D3.js 中的 `d3.quantile()` 函数：

## 例 1

```
<!DOCTYPE html>
<html>
<head>
    <title>
        d3.quantile() function
    </title>
    <script src = "https://d3js.org/d3.v4.min.js"></script>
</head>
<body>
    <script>
        // Initialising a array
        var Array = [10, 20, 30, 40, 50];

        // Calling the d3.quantile() function
        A = d3.quantile(Array, 0);
        B = d3.quantile(Array, 0.25);
        C = d3.quantile(Array, 0.5);
        D = d3.quantile(Array, 0.75);
        E = d3.quantile(Array, 1);

        // Getting the shuffled elements
        document.write(A + "<br>");
        document.write(B + "<br>");
        document.write(C + "<br>");
        document.write(D + "<br>");
        document.write(E + "<br>");
    </script>
</body>
</html>
```

## 输出

```

```

## 例 2

```
<!DOCTYPE html>
<html>
<head>
    <title>
        d3.quantile() function
    </title>
    <script src = "https://d3js.org/d3.v4.min.js"></script>
</head>
<body>
    <script>
        // Initialising an array
        var Array = [10, 20, 30];

        // Calling the d3.quantile() function
        A = d3.quantile(Array, 0);
        B = d3.quantile(Array, 0.25);
        C = d3.quantile(Array, 0.5);
        D = d3.quantile(Array, 0.75);
        E = d3.quantile(Array, 1);

        // Getting the shuffled elements
        document.write(A + "<br>");
        document.write(B + "<br>");
        document.write(C + "<br>");
        document.write(D + "<br>");
        document.write(E + "<br>");
    </script>
</body>
</html>
```

## 输出

```

```

## 参考

`https://devdocs.io/d3~5/d3-array#quantile`