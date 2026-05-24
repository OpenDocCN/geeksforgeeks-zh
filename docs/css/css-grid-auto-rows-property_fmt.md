# CSS grid-auto-rows 属性

> 原文: [https://www.geeksforgeeks.org/css-grid-auto-rows-property/](https://www.geeksforgeeks.org/css-grid-auto-rows-property/)

CSS 中的 `grid-auto-rows` 属性用于指定隐式生成的网格容器的行的大小。

## 语法

```html
grid-auto-rows: auto|max-content|min-content|length|
percentage|minmax(min, max)|initial|inherit;
```

## 属性值

### `auto`
这是默认值。尺寸根据容器的大小隐式确定。

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            CSS grid-auto-rows Property
        </title>
        <style>
            .main {
                display: grid;
                grid-template-areas: "a a";
                grid-gap: 20px;
                padding: 30px;
                background-color: green;
                grid-auto-rows: auto;
            }
            .GFG {
                text-align: center;
                font-size: 35px;
                background-color: white;
                padding: 20px 0;
            }
        </style>
    </head>
    <body>
        <div class="main">
            <div class="GFG">1</div>
            <div class="GFG">2</div>
            <div class="GFG">3</div>
            <div class="GFG">4</div>
            <div class="GFG">5</div>
        </div>
    </body>
</html>
```

**输出:**
![](img/354dc215939c9059eac52c0a6ab022ad.png)

### `length`
用于将 `grid-auto-rows` 属性设置为给定长度。长度值不能为负。

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            CSS grid-auto-rows Property
        </title>
        <style>
            .main {
                display: grid;
                grid-template-areas: "a a";
                grid-gap: 20px;
                padding: 30px;
                background-color: green;
                grid-auto-rows: 3.5cm;
            }
            .GFG {
                text-align: center;
                font-size: 35px;
                background-color: white;
                padding: 20px 0;
            }
        </style>
    </head>
    <body>
        <div class="main">
            <div class="GFG">1</div>
            <div class="GFG">2</div>
            <div class="GFG">3</div>
            <div class="GFG">4</div>
            <div class="GFG">5</div>
        </div>
    </body>
</html>
```

**输出:**
![](img/2f433707bd91bfcca69f438197130e4d.png)

### `percentage`
它将 `grid-auto-rows` 属性设置为百分比值。

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            CSS grid-auto-rows Property
        </title>
        <style>
            .main {
                display: grid;
                grid-template-areas: "a a";
                grid-gap: 20px;
                padding: 30px;
                background-color: green;
                grid-auto-rows: 30%;
            }
            .GFG {
                text-align: center;
                font-size: 35px;
                background-color: white;
                padding: 20px 0;
            }
        </style>
    </head>
    <body>
        <div class="main">
            <div class="GFG">1</div>
            <div class="GFG">2</div>
            <div class="GFG">3</div>
            <div class="GFG">4</div>
            <div class="GFG">5</div>
        </div>
    </body>
</html>
```

**输出:**
![](img/e4034c324d81166f2fcd07efa206154e.png)

### `max-content`
根据容器中最大的物品指定尺寸。

### `min-content`
根据容器中最小的物品指定尺寸。

### `minmax(min, max)`
指定在 `[min, max]` 范围内的尺寸。大于或等于 `min` 且小于或等于 `max`。

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            CSS grid-auto-rows Property
        </title>
        <style>
            .main {
                display: grid;
                grid-template-areas: "a a";
                grid-gap: 20px;
                padding: 30px;
                background-color: green;
                grid-auto-rows: minmax(100px, 3.5cm);
            }
            .GFG {
                text-align: center;
                font-size: 35px;
                background-color: white;
                padding: 20px 0;
            }
        </style>
    </head>
    <body>
        <div class="main">
            <div class="GFG">1</div>
            <div class="GFG">2</div>
            <div class="GFG">3</div>
            <div class="GFG">4</div>
            <div class="GFG">5</div>
        </div>
    </body>
</html>
```

**输出:**
![](img/8afa0d6d2fec7272e045b7c1b83a1dc2.png)

### `initial`
用其默认值初始化。

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            CSS grid-auto-rows Property
        </title>
        <style>
            .main {
                display: grid;
                grid-template-areas: "a a";
                grid-gap: 20px;
                padding: 30px;
                background-color: green;
                grid-auto-rows: initial;
            }
            .GFG {
                text-align: center;
                font-size: 35px;
                background-color: white;
                padding: 20px 0;
            }
        </style>
    </head>
    <body>
        <div class="main">
            <div class="GFG">1</div>
            <div class="GFG">2</div>
            <div class="GFG">3</div>
            <div class="GFG">4</div>
            <div class="GFG">5</div>
        </div>
    </body>
</html>
```

**输出:**
![](img/8e80c99d4ef88ae65d99306c7f33ec7a.png)

### `inherit`
从其父元素继承值。

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            CSS grid-auto-rows Property
        </title>
        <style>
            .container {
                grid-auto-rows: 80px;
            }
            .main {
                display: grid;
                grid-template-areas: "a a";
                grid-gap: 20px;
                padding: 30px;
                background-color: green;
                grid-auto-rows: inherit;
            }
            .GFG {
                text-align: center;
                font-size: 35px;
                background-color: white;
                padding: 20px 0;
            }
        </style>
    </head>
    <body>
        <div class="container">
            <div class="main">
                <div class="GFG">1</div>
                <div class="GFG">2</div>
                <div class="GFG">3</div>
                <div class="GFG">4</div>
                <div class="GFG">5</div>
            </div>
        </div>
    </body>
</html>
```

**输出:**
![](img/8e80c99d4ef88ae65d99306c7f33ec7a.png)

## 支持的浏览器
`grid-auto-rows` 属性支持的浏览器如下：

*   Chrome 57.0
*   Edge 16.0
*   Firefox 52.0
*   Safari 10.0
*   Opera 44.0