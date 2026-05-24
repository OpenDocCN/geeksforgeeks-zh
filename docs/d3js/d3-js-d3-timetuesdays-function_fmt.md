# D3.js

## d3.timeTuesdays() 功能

> 原文: [https://www.geeksforgeeks.org/d3-js-d3-timetuesdays-function/](https://www.geeksforgeeks.org/d3-js-d3-timetuesdays-function/)

D3.js 中的 `d3.timeTuesdays()` 函数用于返回给定起止日期范围内基于星期二的所有日期。

**语法:**

```
d3.timeTuesdays(start, end, step);
```

**参数:** 该函数接受三个参数，如下所示:

*   `start`: 这是给定的开始日期。
*   `end`: 这是给定的结束日期。
*   `step`: 这是用于跳过日期的可选值。

**返回值:** 该函数返回基于星期二的所有日期。

下面的程序说明了 D3.js 中的 `d3.timeTuesdays()` 功能:

**例 1:**

```
<!DOCTYPE html>
<html>

<head>
    <title>
        D3.js | d3.timeTuesdays() Function
    </title>

<script src=
        "https://d3js.org/d3.v4.min.js">
    </script>
</head>

<body>
    <script>

// Initialising start and end date
        var start = new Date(2015, 07, 01);
        var end = new Date(2015, 07, 30);

// Calling the timeTuesdays() function
        // without step value
        var a = d3.timeTuesdays(start, end);

// Getting the Tuesday dates
        console.log(a);
    </script>
</body>

</html>
```

**输出:**

> ["2015-08-03T18:30:00.000Z", "2015-08-10T18:30:00.000Z", "2015-08-17T18:30:00.000Z", "2015-08-24T18:30:00.000Z"]

**例 2:**

```
<!DOCTYPE html>
<html>

<head>
    <title>
        D3.js | d3.timeTuesdays() Function
    </title>

<script src=
        "https://d3js.org/d3.v4.min.js">
    </script>
</head>

<body>
    <script>

// Initialising start and end date
        var start = new Date(2015, 07, 01);
        var end = new Date(2015, 07, 30);

// Calling the timeTuesdays() function
        // with step value
        var a = d3.timeTuesdays(start, end, 2);

// Getting the Tuesday dates
        console.log(a);
    </script>
</body>

</html>
```

**输出:**

```
["2015-08-03T18:30:00.000Z", "2015-08-17T18:30:00.000Z"]
```