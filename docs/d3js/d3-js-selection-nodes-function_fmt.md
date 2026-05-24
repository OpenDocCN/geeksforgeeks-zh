# D3.js selection.nodes()函数

> 原文: [https://www.geeksforgeeks.org/d3-js-selection-nodes-function/](https://www.geeksforgeeks.org/d3-js-selection-nodes-function/)

D3.js 中的 `selection.nodes()` 函数用于返回包含 HTML 元素的选择数组。

**语法:**
```
selection.nodes()
```

**参数:** 此函数不接受任何参数。

**返回值:** 这个函数返回一个元素数组。

## 例1

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width,initial-scale=1.0">
    <script src="https://d3js.org/d3.v4.min.js">
    </script>
    <script src="https://d3js.org/d3-selection.v1.min.js">
    </script>
</head>

<body>
    <div>Some text</div>
    <div>Geeks for geeks</div>
    <div>Geeks for geeks</div>
    <div>Some text</div>

    <script>
        let selection = d3.selectAll("div")
        console.log(selection.nodes())
    </script>
</body>

</html>
```

**输出:**
![](img/3cd04d56ea922851aa71fc0f76e3b37b.png)

## 例2

当给定嵌套容器且选择为空时。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width,initial-scale=1.0">
    <script src="https://d3js.org/d3.v4.min.js">
    </script>
    <script src="https://d3js.org/d3-selection.v1.min.js">
    </script>
</head>

<body>
    <div>Some text</div>
    <div>Geeks for <div>geeks</div>
    </div>
    <div>Geeks <div></div> for geeks</div>
    <div>Some text</div>

    <script>
        let selection = d3.selectAll("div")
        console.log(selection.nodes())
        selection = d3.selectAll("h2")
        console.log(selection.nodes())
    </script>
</body>

</html>
```

**输出:**
![](img/c62fb794debb369f187d9877242a7ca0.png)