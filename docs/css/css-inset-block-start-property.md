# CSS |嵌入块开始属性

> 原文:[https://www . geesforgeks . org/CSS-inset-block-start-property/](https://www.geeksforgeeks.org/css-inset-block-start-property/)

**嵌入块开始属性**用于定义逻辑块开始偏移，而不是用于内联偏移或逻辑块。此属性可以应用于任何写入模式属性。

**语法:**

```html
inset-block-start: length|percentage|auto|inherit|initial|unset;
```

**属性值:**

*   **长度:**设置 px、cm、pt 等定义的固定值。允许负值。它的默认值是 0px。
*   **百分比(%):** 与长度相同，但大小是根据窗口大小的百分比设置的。
*   **自动:**当希望浏览器确定块大小时使用。
*   **初始值:**用于将嵌入块开始属性的值设置为默认值。
*   **inherit:** 当希望元素继承其父元素的 inset-block-start 属性作为自己的属性时使用。
*   **取消设置:**用于取消设置默认插入块开始。

下面的例子说明了 CSS 中的**嵌入块开始属性**:

**例 1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | inset-block-start Property</title>
    <style>
        h1 {
            color: green;
        }

        div {
            background-color: green;
            width: 200px;
            height: 20px;
        }

        .one {
            position: relative;
            inset-block-start: 10px;
            background-color: cyan;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | inset-block-start Property</b>
        <br>
        <br>
        <div>
            <p class="one">
                A Computer Science Portal for Geeks
            </p>
        </div>
    </center>
</body>

</html>                    
```

**输出:**
![](img/55d5ef3894266730e3d283811d03f43f.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | inset-block-start Property</title>
    <style>
        h1 {
            color: green;
        }

        div {
            background-color: green;
            width: 200px;
            height: 120px;
        }

        .one {
            writing-mode: vertical-rl;
            position: relative;
            inset-block-start: 50px;
            background-color: cyan;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | inset-block-start Property</b>
        <br><br>
        <div>
            <p class="one">
                A Computer Science Portal for Geeks
            </p>
        </div>
    </center>
</body>

</html>                    
```

**输出:**
![](img/de6dbcebf7d7dc05784c74248dc77f51.png)

**支持的浏览器:****嵌入块开始属性**支持的浏览器如下:

*   火狐浏览器
*   谷歌 Chrome
*   边缘
*   歌剧

**参考:**[https://developer . Mozilla . org/en-US/docs/Web/CSS/inset-block-start](https://developer.mozilla.org/en-US/docs/Web/CSS/inset-block-start)