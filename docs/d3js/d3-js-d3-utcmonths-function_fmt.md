# d3.utcMonths()

> 原文: [https://www.geeksforgeeks.org/d3-js-d3-utcmonths-function/](https://www.geeksforgeeks.org/d3-js-d3-utcmonths-function/)

`d3.utcMonths()` 函数用于返回在协调世界时（UTC）中，从给定的开始日期到结束日期范围内的所有月份。

## 语法

```
d3.utcMonths(start, end, step);
```

## 参数

该函数接受以下三个参数：

*   `start`：此参数保存给定的开始日期。
*   `end`：此参数保存给定的结束日期。
*   `step`：可选参数，用于指定跳过月份的步长值。

## 返回值

该函数返回给定范围内所有可能的月份。

下面的程序说明了 `d3.utcMonths()` 函数的用法：

## 示例 1

```html
<!DOCTYPE html>
<html>
   <head>
      <title>
          D3.js | d3.utcMonths() Function
      </title>
      <script src="https://d3js.org/d3.v4.min.js"></script>
   </head>
   <body>
      <script>
         // 初始化开始和结束日期
         var start = new Date(2015, 01, 01);
         var end = new Date(2015, 05, 01);

         // 调用 utcMonths() 函数（不带 step 值）
         var a = d3.utcMonths(start, end);

         // 获取月份值
         console.log(a);
      </script>
   </body>
</html>
```

**输出：**

```
["2015-02-01T00:00:00.000Z", "2015-03-01T00:00:00.000Z",
"2015-04-01T00:00:00.000Z", "2015-05-01T00:00:00.000Z"]
```

## 示例 2

```html
<!DOCTYPE html>
<html>
   <head>
      <script src="https://d3js.org/d3.v4.min.js"></script>
      <title>
          D3.js | d3.utcMonths() Function
      </title>
   </head>
   <body>
      <script>
         // 初始化开始和结束日期
         var start = new Date(2015, 01, 01);
         var end = new Date(2015, 05, 01);

         // 调用 utcMonths() 函数（带 step 值）
         var a = d3.utcMonths(start, end, 2);

         // 获取月份值
         console.log(a);
      </script>
   </body>
</html>
```

**输出：**

```
["2015-02-01T00:00:00.000Z", "2015-04-01T00:00:00.000Z"]
```

## 参考

[https://devdocs.io/d3~5/d3-time#timeMonths](https://devdocs.io/d3~5/d3-time#timeMonths)