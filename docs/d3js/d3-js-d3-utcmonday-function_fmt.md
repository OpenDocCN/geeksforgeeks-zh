# D3.js | D3.utcMonday 功能

> 原文: [https://www.geeksforgeeks.org/d3-js-d3-utcmonday-function/](https://www.geeksforgeeks.org/d3-js-d3-utcmonday-function/)

D3.js 中的 `D3.utcMonday` 功能用于返回协调世界时(UTC)中给定的开始和结束日期范围内基于星期一的所有日期。

## 语法:

```
d3.utcMonday.range( start, end, step );
```

## 参数:
该函数接受三个参数，如下所述:

*   `start`: 此参数保存给定的开始日期。
*   `end`: 此参数保存给定的结束日期。
*   `step`: 一个可选参数，用于保存跳过日期的值。

## 返回值:
该函数返回基于周一的所有日期。

以下程序说明了 D3.js 中的 `D3.utcMonday` 功能:

## 例 1:

```
<!DOCTYPE html>
<html>

<head>
    <title>
        D3.js | d3.utcMonday Function
    </title>

<script src = 
        "https://d3js.org/d3.v4.min.js">
    </script>
</head>

<body>
    <script>

// Initialising start and end date
        var start = new Date(2015, 07, 01);
        var end = new Date(2015, 07, 30);

// Calling the utcMonday function
        // without step value
        var a = d3.utcMonday.range(start, end);

// Getting the Monday dates
        console.log(a);
    </script>
</body>

</html>
```

### 输出:

```
["2015-08-03T00:00:00.000Z", "2015-08-10T00:00:00.000Z", 
"2015-08-17T00:00:00.000Z", "2015-08-24T00:00:00.000Z"]
```

## 例 2:

```
<!DOCTYPE html>
<html>

<head>
    <title>
        D3.js | d3.utcMonday Function
    </title>
    <script src = 
        "https://d3js.org/d3.v4.min.js">
    </script>
</head>

<body>
    <script>

// Initialising start and end date
        var start = new Date(2015, 07, 01);
        var end = new Date(2015, 07, 30);

// Calling the utcMonday function
        // with step value
        var a = d3.utcMonday.range(start, end, 2);

// Getting the Monday dates
        console.log(a);
    </script>
</body>

</html>
```

### 输出:

```
["2015-08-03T00:00:00.000Z", "2015-08-17T00:00:00.000Z"]
```

参考: [https://devdocs.io/d3~5/d3-time#timeMonday](https://devdocs.io/d3~5/d3-time#timeMonday)