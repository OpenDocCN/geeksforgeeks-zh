# 如何以 n 列格式显示列表？

> 原文：[https://www.geeksforgeeks.org/how-to-display-a-list-in-n-columns-format/](https://www.geeksforgeeks.org/how-to-display-a-list-in-n-columns-format/)

我们可以通过两种方式以 n 列格式显示列表：

1.  [使用列表中的浮动](#no_1)
2.  [使用列表中的列数](#no_2)

## 使用列表中的浮动

使用 `float`，我们可以让列表项向左浮动，即紧随其后的下一个项目将显示在左侧。因此，这里我们将 `ol` 的大小设置为 `30em`，一个列表项的大小设置为 `10em`，这样一行只能容纳 3 个项目，从而形成三列。要获得所需的列数，您可以相应地设置 `ol` 和一个项目的大小。

**例 1:**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <title>
        How to display a list in
        n columns format?    
    </title>

<!--CSS Code-->
    <style media="screen">
        body{
            background: orange;
            overflow: hidden;
        }
        h1 {
            text-align: center;
            color: green;
        }
        ol{
            /* As width is 10 so it
            will create 3 columns */
            width: 30em;

            /* Removes any style
               in list */
            list-style: none;
            color: white;
            position: absolute;
        }
        ol li{
            /* Makes the list to
               float left */
            float: left;

            /* Size of one list item */
            width: 10em;
        }
        br {
            clear: left;
        }

        /* Creates gap between
            two two columns */
        div.wrapper {
            margin-bottom: 1em;
        }
    </style>
</head>

<body>
    <!-- HTML Code -->
    <h1>Geeks For Geeks</h1>
    <center>
        <div class="wrapper">
            <ol>
                <li>Geek 1</li>
                <li>Geek 2</li>
                <li>Geek 3</li>
                <li>Geek 4</li>
                <li>Geek 5</li>
                <li>Geek 6</li>
                <li>Geek 7</li>
                <li>Geek 8</li>
                <li>Geek 9</li>
                <li>Geek 10</li>
                <li>Geek 11</li>
                <li>Geek 12</li>
            </ol>
        </div>
    </center>
</body>

</html>
```

**输出:**
![](img/5b4cf49cb5576150bbcec80158098c92.png)

## 使用列表中的列数

CSS 中的 `column-count` 属性可帮助您决定输出中所需的列数。它的值可以是任何正整数。这里是一个使用两个不同 `n` 值（`n = 6`，`n = 4`）的示例。

**例 2:**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="utf-8">

    <title>
        How to display a list in
        n columns format?
    </title>

<!--CSS Code-->
    <style media="screen">
        body{
            background: dodgerblue;
            overflow: hidden;
        }

        h1 {
            text-align: center;
            color: green;
        }

        /* Here value of column-count can
           be any positive integer value */
        ol.no_1{
            /* Divides into 4 columns */
            column-count: 4;

            /* Removes any style in list */
            list-style: none;
            height: 300px;
            top: 10%;
            left:15%;
            color: white;
            position: absolute;
        }
        ol.no_2{
            /* Divides into 6 columns */
            column-count: 6;

            /* Removes any style in list */
            list-style: none;
            height: 300px;
            top:35%;
            left:5%;
            color: white;
            position: absolute;
        }
        ol li{
            /* It is the necessary statement
               as it makes it compactile
               with the height of ol */
            display: inline-block;
        }
    </style>
</head>

<body>
    <!-- HTML Code -->
    <h1>Geeks For Geeks</h1>

    <div class="wrapper">

        <!-- Class with n=4 -->
        <ol class="no_1">
            <li>Geek 1</li>
            <li>Geek 2</li>
            <li>Geek 3</li>
            <li>Geek 4</li>
            <li>Geek 5</li>
            <li>Geek 6</li>
            <li>Geek 7</li>
            <li>Geek 8</li>
            <li>Geek 9</li>
            <li>Geek 10</li>
            <li>Geek 11</li>
            <li>Geek 12</li>
        </ol>

        <!-- Class with n=6 -->
        <ol class="no_2">
            <li>Geek 1</li>
            <li>Geek 2</li>
            <li>Geek 3</li>
            <li>Geek 4</li>
            <li>Geek 5</li>
            <li>Geek 6</li>
            <li>Geek 7</li>
            <li>Geek 8</li>
            <li>Geek 9</li>
            <li>Geek 10</li>
            <li>Geek 11</li>
            <li>Geek 12</li>
        </ol>
    </div>
</body>

</html>
```

**输出:**
![](img/395fb9bd8487abfdf18d3f43555e8427.png)