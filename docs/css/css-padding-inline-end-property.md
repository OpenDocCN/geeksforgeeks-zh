# CSS |填充-内联-结束属性

> 原文:[https://www . geesforgeks . org/CSS-padding-inline-end-property/](https://www.geeksforgeeks.org/css-padding-inline-end-property/)

CSS 中的**填充行内结束属性**用于定义元素的逻辑块结束填充。此属性有助于根据元素的书写模式、方向和文本方向放置填充。
**语法:**

```html
padding-inline-end: length|percentage|auto|inherit|initial|unset;
```

**房产价值:**

*   **长度:**设置 px、cm、pt 等定义的固定值。允许负值。它的默认值是 0px。
*   **百分比:**用于根据元素宽度的百分比设置填充行内结束值。
*   **自动:**当希望浏览器确定块大小时使用。
*   **初始值:**用于将块大小属性的值设置为默认值。
*   **inherit:** 当希望元素继承其父元素的块大小属性作为自己的属性时使用。
*   **取消设置:**用于取消设置默认块大小。

以下示例说明了 CSS 中的**填充-内联-结束属性**:
**示例 1:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | padding-inline-end Property</title>
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
            padding-inline-end: 40px;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | padding-inline-end Property</b>
        <br><br>
        <div class="one">A Computer</div>
        <div class="two">Science Portal</div>
        <div class="three">For Geeks</div>
    </center>
</body>

</html>                   
```

**输出:**

![](img/18a7c957d2ab7dd55d74dd3212cc48b1.png)

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | padding-inline-end Property</title>
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
            padding-inline-end: 20px;
            writing-mode: vertical-lr;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | padding-inline-end Property</b>
        <br><br>
        <div class="one">A Computer</div>
        <div class="two">Science Portal</div>
        <div class="three">For Geeks</div>
    </center>
</body>

</html>                                      
```

**输出:**

![](img/caf22ad2c1752c379068f76675075c1a.png)

**支持的浏览器:****填充内联结束属性**支持的浏览器如下:

*   火狐浏览器
*   谷歌 Chrome
*   边缘
*   歌剧

**参考:**[https://developer . Mozilla . org/en-US/docs/Web/CSS/padding-inline-end](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-inline-end)