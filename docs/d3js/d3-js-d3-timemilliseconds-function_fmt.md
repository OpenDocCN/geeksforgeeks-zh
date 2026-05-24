# D3.js | D3.timeMilliseconds()函数

> 原文: [https://www.geeksforgeeks.org/d3-js-d3-timemilliseconds-function/](https://www.geeksforgeeks.org/d3-js-d3-timemilliseconds-function/)

D3.js 中的 `D3.timeMilliseconds()` 函数用于返回给定开始和结束时间范围内所有带有日期的毫秒。

**语法:**

```
d3.timeMilliseconds(start, end, step);
```

**参数:** 该函数接受以下给出的三个参数:

*   `start`: 这是给定的开始时间。
*   `end`: 这是给定的结束时间。
*   `step`: 这是用于跳过毫秒的可选值。

**返回值:** 该函数返回给定范围内所有可能的毫秒数。

下面的程序说明了 D3.js 中的 `D3.timeMilliseconds()` 功能:

## 示例 1:

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        d3.timeMilliseconds() Function
    </title>
    <script src="https://d3js.org/d3.v4.min.js">
  </script>
</head>

<body>

<script>
        // Initialising start and end time
        var start = new Date(2015, 07, 01, 4, 20, 10, 1);
        var end = new Date(2015, 07, 01, 4, 20, 10, 5);

// Calling the timeMilliseconds() function
        // without step value
        var a = d3.timeMilliseconds(start, end);

// Getting the millisecond values
        console.log(a);
    </script>
</body>

</html>
```

**输出:**

```
["2015-07-31T22:50:10.001Z", "2015-07-31T22:50:10.002Z", 
"2015-07-31T22:50:10.003Z", "2015-07-31T22:50:10.004Z"]
```

## 示例 2:

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        d3.timeMilliseconds() Function
    </title>
    <script src="https://d3js.org/d3.v4.min.js">
  </script>
</head>

<body>

<script>
        // Initialising start and end time
        var start = new Date(2015, 07, 01, 4, 20, 10, 1);
        var end = new Date(2015, 07, 01, 4, 20, 10, 5);

// Calling the timeMilliseconds() function
        // with step value
        var a = d3.timeMilliseconds(start, end, 2);

// Getting the millisecond values
        console.log(a);
    </script>
</body>

</html>
```

**输出:**

```
["2015-07-31T22:50:10.001Z", "2015-07-31T22:50:10.003Z"]
```

**参考:** [https://devdocs.io/d3~5/d3-time#timeMilliseconds](https://devdocs.io/d3~5/d3-time#timeMilliseconds)