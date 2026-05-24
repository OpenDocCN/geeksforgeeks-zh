# D3.js 中的 `d3.scaleIdentity()` 函数

> 原文：[https://www.geeksforgeeks.org/d3-js-d3-scaleidentity-function/](https://www.geeksforgeeks.org/d3-js-d3-scaleidentity-function/)

D3.js 中的 `d3.scaleIdentity()` 函数用来构造单位域为 `[0, 1]`、单位范围为 `[0, 1]` 的新的身份尺度。

## 语法

```
d3.scaleIdentity().domain(array of values).range(array of values);
```

## 参数

此函数不接受任何参数。

## 返回值

该函数返回该域值对应的范围。

下面的程序说明了 D3.js 中的 `d3.scaleIdentity()` 功能：

## 示例

```html
<!DOCTYPE html>
<html>

<head>
    <title></title>
    <script src="https://d3js.org/d3.v4.min.js">
  </script>
</head>

<body>

<script>
        // Calling the scaleIdentity() function
        var A = d3.scaleIdentity()
            .domain([0, 1])
            .range([0, 1]);

        // Getting the corresponding range for
        // the domain value
        console.log(A('0'));
        console.log(A('1'));
    </script>
</body>

</html>
```

## 输出

```

```

## 参考

[https://devdocs.io/d3~5/d3-scale#scaleBand](https://devdocs.io/d3~5/d3-scale#scaleBand)