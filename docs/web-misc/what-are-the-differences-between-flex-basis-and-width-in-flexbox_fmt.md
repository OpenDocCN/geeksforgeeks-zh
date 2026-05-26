# Flexbox 中的 flex-basis 和 width 有什么区别？

> 原文：[https://www.geeksforgeeks.org/what-are-the-differences-between-flex-basis-and-width-in-flexbox/](https://www.geeksforgeeks.org/what-are-the-differences-between-flex-basis-and-width-in-flexbox/)

本文描述了 `flex-basis` 和 `width` 属性之间的区别以及用法示例。`flex-basis` 属性根据 `flex-direction` 值定义 flex 项目的初始大小。它具有以下可以改变其行为的附加属性：

*   `flex-direction` 值可以设置为 `row` 或 `column`。如果其值为 `row`，则定义宽度；如果其值为 `column`，则定义高度。
*   `flex-basis` 属性只能应用于 flex 项目，`width` 属性可以应用于所有元素。
*   使用 `flex` 属性时，flex 项的所有三个属性，即 `flex-grow`、`flex-shrink` 和 `flex-basis` 可以组合成一个声明，但是使用 `width`，做同样的事情需要多行代码。
*   如果 `flex-direction` 值设置为 `column`，则使用 `width` 属性来调整 flex 项目的水平尺寸。

以下示例显示了 `flex-basis` 与 `width` 和 `height` 属性之间的差异：

**示例 1：** 当 `flex-direction` 设置为 `row` 时，使用 `flex-basis`。

## HTML

```html
<!DOCTYPE html>
<html>

<head>
    <title>FlexBox</title>
    <style>
        body {
            background: #eee;
        }

        h1 {
            color: green;
        }

        .wrapper {
            width: 100%;
            margin: 0 auto;
        }

        .flex-container {
            display: flex;
            background: #fff;
            flex-wrap: wrap;
            flex-direction: row;
        }

        .box {
            /*
      Since flex-direction is set to
      row therefore flex-basis defines
      the width. Either of the width
      property or flex-basis property
      can be used as both perform
      a similar task in this case.
      */
            height: 100px;
            flex-basis: 600px;
        }

        .one {
            background: red;
        }

        .two {
            background: blue;
        }

        .three {
            background: green;
        }
    </style>
</head>

<body>
    <h1>GeeksForGeeks</h1>
    <h2>Flex-basis vs Width </h2>
    <br>
    <div class="wrapper">
        <div class="flex-container">
            <div class="box one"></div>
            <div class="box two"></div>
            <div class="box three"></div>
        </div>
    </div>
</body>

</html>
```

**输出：**

![](img/b28b1d605e83fc0648ea09ac51155f69.png)

**示例 2：** 当 `flex-direction` 设置为 `column` 时，使用 `flex-basis`。

## HTML

```html
<!DOCTYPE html>
<html>

<head>
    <title>FlexBox</title>
    <style>
        body {
            background: #eee;
        }

        h1 {
            color: green;
        }

        .wrapper {
            width: 100%;
            margin: 0 auto;
        }

        .flex-container {
            display: flex;
            background: #fff;
            flex-wrap: wrap;
            flex-direction: column;
        }

        .box {
            /*
      Since flex-direction is set to
      column therefore flex-basis defines
      the height and hence overrides the
      height property. The height of
      flex-item will therefore be 80px.
      The width property has to be separately
      assigned a horizontal width.
      */
            height: 100px;
            width: 100px;
            flex-basis: 80px;
        }

        .one {
            background: red;
        }

        .two {
            background: blue;
        }

        .three {
            background: green;
        }
    </style>
</head>

<body>
    <h1>GeeksForGeeks</h1>
    <h2>Flex-basis vs Width </h2>
    <br>
    <div class="wrapper">
        <div class="flex-container">
            <div class="box one"></div>
            <div class="box two"></div>
            <div class="box three"></div>
        </div>
    </div>
</body>

</html>
```

**输出：**

![](img/4220c4913c8bfd85f4e7618711c86dd9.png)