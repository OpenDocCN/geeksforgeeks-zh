# D3.js | D3.utcMondays() 函数

> 原文: [https://www.geeksforgeeks.org/d3-js-d3-utcmondays-function/](https://www.geeksforgeeks.org/d3-js-d3-utcmondays-function/)

D3.js 中的 `d3.utcMondays()` 函数用于返回以协调世界时（UTC）中给定的开始和结束日期范围内基于星期一的所有日期。

## 语法

```
d3.utcMondays( start, end, step );
```

## 参数

该函数接受下面给出的三个参数：

*   `start`：此参数保存给定的开始日期。
*   `end`：此参数保存给定的结束日期。
*   `step`：是一个可选参数，用于跳过日期的值。

## 返回值

该函数返回基于周一的所有日期。

下面的程序说明了 D3.js 中的 `d3.utcMondays()` 功能：

## 示例

### 示例 1

```
<!DOCTYPE html>
<html>

<head>
    <title>
        D3.js | d3.utcMondays() Function
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

// Calling the utcMondays() function
        // without step value
        var a = d3.utcMondays(start, end);

// Getting the Monday dates
        console.log(a);
    </script>
</body>

</html>                 
```

#### 输出

```
["2015-08-03T00:00:00.000Z", "2015-08-10T00:00:00.000Z",
"2015-08-17T00:00:00.000Z", "2015-08-24T00:00:00.000Z"]
```

### 示例 2

```
<!DOCTYPE html>
<html>

<head>
    <title>
        D3.js | d3.utcMondays() Function
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

// Calling the utcMondays() function
        // with step value
        var a = d3.utcMondays(start, end, 2);

// Getting the Monday dates
        console.log(a);
    </script>
</body>

</html>     
```

#### 输出

```
["2015-08-03T00:00:00.000Z", "2015-08-17T00:00:00.000Z"]
```

## 参考

[https://devdocs.io/d3~5/d3-time#timeMondays](https://devdocs.io/d3~5/d3-time#timeMondays)