# D3.js | d3.utcSaturdays() 函数

> 原文: [https://www.geeksforgeeks.org/d3-js-d3-utcsaturdays-function/](https://www.geeksforgeeks.org/d3-js-d3-utcsaturdays-function/)

`d3.utcSaturdays()` 函数用于返回以协调世界时（UTC）中给定的开始和结束日期范围内基于星期六的所有日期。

## 语法

```
d3.utcSaturdays(start, end, step);
```

## 参数

该函数接受以下三个参数：

*   `start`：给定的开始日期。
*   `end`：给定的结束日期。
*   `step`：可选值，用于跳过日期。

## 返回值

该函数返回基于周六的所有日期。

下面的程序说明了 D3.js 中的 `d3.utcSaturdays()` 函数：

### 例 1

```
<!DOCTYPE html>
<html>
<head>
    <title>
        D3.js | d3.utcSaturdays() Function
    </title>
    <script src="https://d3js.org/d3.v4.min.js"></script>
</head>
<body>
    <script>
        // Initialising start and end date
        var start = new Date(2015, 07, 01);
        var end = new Date(2015, 07, 30);

        // Calling the utcSaturdays() function
        // without step value
        var a = d3.utcSaturdays(start, end);

        // Getting the Saturday dates
        console.log(a);
    </script>
</body>
</html>
```

**输出:**

```
["2015-08-01T00:00:00.000Z", "2015-08-08T00:00:00.000Z", "2015-08-15T00:00:00.000Z", "2015-08-22T00:00:00.000Z", "2015-08-29T00:00:00.000Z"]
```

### 例 2

```
<!DOCTYPE html>
<html>
<head>
    <title>
        D3.js | d3.utcSaturdays() Function
    </title>
    <script src="https://d3js.org/d3.v4.min.js"></script>
</head>
<body>
    <script>
        // Initialising start and end date
        var start = new Date(2015, 07, 01);
        var end = new Date(2015, 07, 30);

        // Calling the utcSaturdays() function
        // with step value
        var a = d3.utcSaturdays(start, end, 2);

        // Getting the Saturday dates
        console.log(a);
    </script>
</body>
</html>
```

**输出:**

```
["2015-08-01T00:00:00.000Z", "2015-08-15T00:00:00.000Z", "2015-08-29T00:00:00.000Z"]
```

**参考:** [https://devdocs.io/d3~5/d3-time#timeSaturdays](https://devdocs.io/d3~5/d3-time#timeSaturdays)