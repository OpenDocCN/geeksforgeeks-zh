# D3.js | `d3.continuous.invert()`函数

> 原文: [https://www.geeksforgeeks.org/d3-js-d3-continuous-invert-function/](https://www.geeksforgeeks.org/d3-js-d3-continuous-invert-function/)

D3.js 中的 `d3.continuous.invert()` 函数用于在给定范围内的值的情况下从域中返回相应的值。

## 语法

```
.invert( value )
```

## 参数

该功能接受保存范围值的单参数 `value`。

## 返回值

如果给定范围内的值，则该函数从域中返回相应的值。

下面的程序说明了 D3.js 中的 `d3.continuous.invert()` 函数:

## 例 1

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        D3.js | d3.continuous.invert() Function
    </title>

<script src = 
        "https://d3js.org/d3.v4.min.js">
    </script>
</head>

<body>
    <script>

// Calling scaleLinear() function
        var x = d3.scaleLinear().domain([10, 150])
                    .range([0, 1000]);

// Calling the .invert() function
        // and getting the corresponding value
        // from domain if value from range is given
        console.log(x.invert(150)); 
        console.log(x.invert(999));
    </script>
</body>

</html>
```

## 输出

```
149.86
```

## 例 2

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        D3.js | d3.continuous.invert() Function
    </title>

<script src = 
        "https://d3js.org/d3.v4.min.js">
    </script>
</head>

<body>
    <script>

// Calling scaleLinear() function
        var x = d3.scaleLinear().domain([0, 1])
                .range([10, 20]);

// Calling the .invert() function
        // and getting the corresponding value
        // from domain if value from range is given
        console.log(x.invert(11)); 
        console.log(x.invert(13));
        console.log(x.invert(15)); 
        console.log(x.invert(19));

</script>
</body>
</html>
```

## 输出

```
0.1
0.3
0.5
0.9
```

## 参考

[https://devdocs.io/d3~5/d3-scale#continuous_invert](https://devdocs.io/d3~5/d3-scale#continuous_invert)