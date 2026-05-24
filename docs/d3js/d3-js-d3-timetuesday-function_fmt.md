# D3.js | `d3.timeTuesday` 函数

> 原文：[https://www.geeksforgeeks.org/d3-js-d3-timetuesday-function/](https://www.geeksforgeeks.org/d3-js-d3-timetuesday-function/)

D3.js 中的 `d3.timeTuesday` 函数用于返回给定起止日期范围内基于星期二的所有日期。

## 语法

```
d3.timeTuesday.range( start, end, step );
```

## 参数

该函数接受下面给出的三个参数：

*   `Start`：此参数保存给定的开始日期。
*   `End`：此参数保存给定的结束日期。
*   `Step`：一个可选参数，用于保存跳过日期的步长值。

## 返回值

该函数返回基于星期二的所有日期。

下面的程序说明了 D3.js 中的 `d3.timeTuesday` 功能：

### 例 1

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        D3.js | d3.timeTuesday Function
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

// Calling the timeTuesday function
        // without step value
        var a = d3.timeTuesday.range(start, end);

// Getting the Tuesday dates
        console.log(a);
    </script>
</body>

</html>
```

**输出：**

```
["2015-08-03T18:30:00.000Z", "2015-08-10T18:30:00.000Z", 
"2015-08-17T18:30:00.000Z", "2015-08-24T18:30:00.000Z"]
```

### 例 2

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        D3.js | d3.timeTuesday Function
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

// Calling the timeTuesday function
         // with step value
         var a = d3.timeTuesday.range(start, end, 2);

// Getting the Tuesday dates
         console.log(a);
    </script>
</body>

</html>
```

**输出：**

```
["2015-08-03T18:30:00.000Z", "2015-08-17T18:30:00.000Z"]
```

## 参考

[T2] https://devdocs.io/d3~5/d3-time#timeTuesday