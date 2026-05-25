# HTML DOM 样式 fontVariant 属性

> 原文：[https://www.geeksforgeeks.org/html-dom-style-fontvariant-property/](https://www.geeksforgeeks.org/html-dom-style-fontvariant-property/)

DOM HTML 中的 `style.fontVariant` 属性用于设置大写字母的字体。该属性主要将小写字母转换为大写字母，但与其余文本相比，这些字母的字体较小。

## 语法

它返回 `fontVariant` 属性。

```html
object.style.fontVariant
```

它用于设置 `fontVariant` 属性。

```html
object.style.fontVariant = "normal|small-caps|initial|inherit"
```

## 值

| 值 | 描述 |
| --- | --- |
| normal | 带有普通文本的默认值。 |
| small-caps | 小写字母字体 |
| initial | 设置为默认值 |
| inherit | 从父元素继承属性 |

## 返回值

它返回一个用小写字母表示字体的字符串。

## 示例-1

```html
<!DOCTYPE html>
<html>
<head>
    <title>DOM Style fontVariant Property </title>
</head>
<body>
    <center>
        <h1 style="color:green;width:40%;"> 
            GeeksForGeeks 
        </h1>
        <h2>DOM Style fontVariant Property </h2>
        <p id="gfg">
            A computer science portal for geeks
        </p>
        <button type="button" onclick="geeks()">
            Submit
        </button>
        <script>
            function geeks() {
                // Set fontVariant
                document.getElementById("gfg").style.fontVariant = "small-caps";
            }
        </script>
    </center>
</body>
</html>
```

## 输出

之前点击按钮：
![](img/c066c1940fdcf90d3dfd7edb27d44d2d.png)

点击按钮后：
![](img/9d8560bf1bff1abf93474b246db491aa.png)

## 示例-2

```html
<!DOCTYPE html>
<html>
<head>
    <title>DOM Style fontVariant Property </title>
</head>
<body>
    <center>
        <h1 style="color:green;width:40%;"> 
            GeeksForGeeks 
        </h1>
        <h2>DOM Style fontVariant Property </h2>
        <p id="gfg">
            A computer science portal for geeks
        </p>
        <button type="button" onclick="geeks()">
            Submit
        </button>
        <script>
            function geeks() {
                // Set fontVariant
                document.getElementById("gfg").style.fontVariant = "all-small-caps";
            }
        </script>
    </center>
</body>
</html>
```

## 输出

之前点击按钮：
![](img/c066c1940fdcf90d3dfd7edb27d44d2d.png)

点击按钮后：
![](img/3825157f8ce2703dc8611c83a8feed1d.png)

## 支持的浏览器

由 `style.fontVariant` 属性支持的浏览器如下：

*   Google Chrome
*   Microsoft Edge
*   Firefox
*   Opera
*   Safari