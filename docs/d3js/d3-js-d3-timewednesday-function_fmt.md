# D3.js | d3.timeWednesday() 功能

> 原文: [https://www.geeksforgeeks.org/d3-js-d3-timewednesday-function/](https://www.geeksforgeeks.org/d3-js-d3-timewednesday-function/)

D3.js 中的 `d3.timeWednesday` 功能用于返回给定起止日期范围内所有基于星期三的日期。

## 语法

```
d3.timeWednesday.range(start, end, step);
```

## 参数

该函数接受下面给出的三个参数:

*   `start`: 此参数保存给定的开始日期。
*   `end`: 此参数保存给定的结束日期。
*   `step`: 这是一个可选值，用于跳过日期。

## 返回值

该函数返回基于周三的所有日期。

下面的程序说明了 D3.js 中的 `d3.timeWednesday` 功能:

### 例 1

```html
<!DOCTYPE html>
<html>
      <head>
      <title>
          D3.js | d3.timeWednesday() Function 
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

// Calling the timeWednesday function
         // without step value
         var a = d3.timeWednesday.range(start, end);

// Getting the Wednesday dates
         console.log(a);
      </script>
   </body>
</html>
```

**输出:**

```
["2015-08-04T18:30:00.000Z", "2015-08-11T18:30:00.000Z",
 "2015-08-18T18:30:00.000Z", "2015-08-25T18:30:00.000Z"]
```

### 例 2

```html
<!DOCTYPE html>
<html>
   <head>
      <title>
          D3.js | d3.timeWednesday() Function 
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

// Calling the timeWednesday function
         // with step value
         var a = d3.timeWednesday.range(start, end, 2);

// Getting the Wednesday dates
         console.log(a);
      </script>
   </body>
</html>
```

**输出:**

```
["2015-08-04T18:30:00.000Z", "2015-08-18T18:30:00.000Z"]
```

**参考:** [https://devdocs.io/d3~5/d3-time#timeWednesday](https://devdocs.io/d3~5/d3-time#timeWednesday)