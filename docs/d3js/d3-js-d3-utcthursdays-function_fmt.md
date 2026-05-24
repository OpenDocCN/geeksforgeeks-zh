# D3.js | D3.utcThursdays() Function

> 原文: [https://www.geeksforgeeks.org/d3-js-d3-utcthursdays-function/](https://www.geeksforgeeks.org/d3-js-d3-utcthursdays-function/)

`D3.utcThursdays()` 函数用于返回协调世界时 (UTC) 中给定的开始和结束日期范围内基于星期四的所有日期。

**语法:**

```
d3.utcThursdays( start, end, step );
```

**参数:** 该函数接受下面给出的三个参数:

*   `start`: 此参数保存给定的开始日期。
*   `end`: 此参数保存给定的结束日期。
*   `step`: 一个可选参数，用于保存跳过日期的值。

**返回值:** 该函数返回基于周四的所有日期。

下面的程序说明了 D3.js 中的 `D3.utcThursdays()` 函数:

**例 1:**

```
<!DOCTYPE html>
<html>
<head>
    <title>
        D3.js | d3.utcThursdays() Function
    </title>
    <script src="https://d3js.org/d3.v4.min.js"></script>
</head>
<body>
    <script>
        // Initialising start and end date
        var start = new Date(2015, 07, 01);
        var end = new Date(2015, 07, 30);

        // Calling the utcThursdays() function
        // without step value
        var a = d3.utcThursdays(start, end);

        // Getting the Thursday dates
        console.log(a);
    </script>
</body>
</html>
```

**输出:**

```
["2015-08-06T00:00:00.000Z", "2015-08-13T00:00:00.000Z", 
"2015-08-20T00:00:00.000Z", "2015-08-27T00:00:00.000Z"]
```

**例 2:**

```
<!DOCTYPE html>
<html>
<head>
    <title>
        D3.js | d3.utcThursdays() Function
    </title>
    <script src="https://d3js.org/d3.v4.min.js"></script>
</head>
<body>
    <script>
        // Initialising start and end date
        var start = new Date(2015, 07, 01);
        var end = new Date(2015, 07, 30);

        // Calling the utcThursdays() function
        // with step value
        var a = d3.utcThursdays(start, end, 2);

        // Getting the Thursday dates
        console.log(a);
    </script>
</body>
</html>
```

**输出:**

```
["2015-08-06T00:00:00.000Z", "2015-08-20T00:00:00.000Z"]
```

**参考:** [https://devdocs.io/d3~5/d3-time#timeThursdays](https://devdocs.io/d3~5/d3-time#timeThursdays)