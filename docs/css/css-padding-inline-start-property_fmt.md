# CSS `padding-inline-start` 属性

> 原文：[https://www.geeksforgeeks.org/css-padding-inline-start-property/](https://www.geeksforgeeks.org/css-padding-inline-start-property/)

CSS 中的 `padding-inline-start` 属性用于定义元素的逻辑块开始填充。此属性有助于根据元素的书写模式、方向和文本方向放置填充。

**语法：**

```html
padding-inline-start: length|percentage|auto|inherit|initial|unset;
```

**属性值：**

*   `length`：设置 `px`、`cm`、`pt` 等定义的固定值。也允许负值。它的默认值是 `0px`。
*   `percentage`：与 `length` 相同，但填充是根据窗口大小的百分比设置的。
*   `auto`：当浏览器确定 `padding-inline-start` 属性大小时使用。
*   `initial`：用于将 `padding-inline-start` 属性的值设置为默认值。
*   `inherit`：当希望元素从其父元素继承 `padding-inline-start` 属性时使用。
*   `unset`：用于取消设置默认 `padding-inline-start` 属性。

以下示例说明了 CSS 中的 `padding-inline-start` 属性：

## 示例 1

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | padding-inline-start Property</title>
    <style>
        h1 {
            color: green;
        }

        div {
            background-color: yellow;
            width: 110px;
            height: 80px;
        }
        .two {
            padding-inline-start: 40px;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | padding-inline-start Property</b>
        <br><br>
        <div class="one">A Computer</div>
        <div class="two">Science Portal</div>
        <div class="three">For Geeks</div>
    </center>
</body>

</html>
```

**输出：**

![](img/41cf5f862e017926d76dd6924be619ee.png)

## 示例 2

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | padding-inline-start Property</title>
    <style>
        h1 {
            color: green;
        }

        div {
            background-color: yellow;
            width: 110px;
            height: 80px;
        }
        .two {
            padding-inline-start: 20px;
            writing-mode: vertical-lr;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | padding-inline-start Property</b>
        <br><br>
        <div class="one">A Computer</div>
        <div class="two">Science Portal</div>
        <div class="three">For Geeks</div>
    </center>
</body>

</html>
```

**输出：**

![](img/6bb98aff18134e79204fecc3a8a0cb65.png)

**支持的浏览器：** 由 `padding-inline-start` 属性支持的浏览器如下：

*   Firefox
*   Google Chrome
*   Edge
*   Opera

**参考：** [https://developer.mozilla.org/en-US/docs/Web/CSS/padding-inline-start](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-inline-start)