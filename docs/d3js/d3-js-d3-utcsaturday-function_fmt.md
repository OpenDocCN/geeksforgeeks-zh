# D3.js | D3.utcSaturday 功能

> 原文: [https://www.geeksforgeeks.org/d3-js-d3-utcsaturday-function/](https://www.geeksforgeeks.org/d3-js-d3-utcsaturday-function/)

D3.js 中的 `D3.utcSaturday.range` 功能用于返回给定的开始和结束日期协调世界时(UTC)范围内基于星期六的所有日期。

## 语法

```
d3.utcSaturday.range(start, end, step);
```

## 参数

该功能接受以下给出的三个参数:

*   `start`: This is the given start date.
*   `end`: This is the given end date.
*   `step`: This is an optional value for skipping the date.

## 返回值

该函数返回基于周六的所有日期。

下面的程序说明了 D3.js 中的 `D3.utcSaturday.range` 功能:

### 例 1

```
<!DOCTYPE html>
<html>
<head>
    <title>
        D3.js | d3.utcSaturday Function
    </title>
    <script src="https://d3js.org/d3.v4.min.js"></script>
</head>
<body>
    <script>
        // Initialising start and end date
        var start = new Date(2015, 07, 01);
        var end = new Date(2015, 07, 30);

        // Calling the utcSaturday function
        // without step value
        var a = d3.utcSaturday.range(start, end);

        // Getting the Saturday dates
        console.log(a);
    </script>
</body>
</html>
```

### 输出

> ["2015-08-01T00:00:00.000Z", "2015-08-08T00:00:00.000Z", "2015-08-15T00:00:00.000Z", "2015-08-22T00:00:00.000Z", "2015-08-29T00:00:00.000Z"]

### 例 2

```
<!DOCTYPE html>
<html>
<head>
    <title>
        D3.js | d3.utcSaturday Function
    </title>
    <script src="https://d3js.org/d3.v4.min.js"></script>
</head>
<body>
    <script>
        // Initialising start and end date
        var start = new Date(2015, 07, 01);
        var end = new Date(2015, 07, 30);

        // Calling the utcSaturday function
        // with step value
        var a = d3.utcSaturday.range(start, end, 2);

        // Getting the Saturday dates
        console.log(a);
    </script>
</body>
</html>
```

### 输出

```
["2015-08-01T00:00:00.000Z", "2015-08-15T00:00:00.000Z", "2015-08-29T00:00:00.000Z"]
```

## 参考

[https://devdocs.io/d3~5/d3-time#timeSaturday](https://devdocs.io/d3~5/d3-time#timeSaturday)