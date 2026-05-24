# CSS |内嵌属性

> 原文:[https://www.geeksforgeeks.org/css-inset-inline-property/](https://www.geeksforgeeks.org/css-inset-inline-property/)

CSS 中的**内嵌属性**用于定义逻辑内嵌的开始和结束偏移量，而不是块偏移量或逻辑块。此属性可以应用于任何写入模式属性。

**语法:**

```html
inset-inline: length|percentage|auto|inherit|initial|unset;
```

**属性值:**

*   **长度:**设置 px、cm、pt 等定义的固定值。允许负值。它的默认值是 0px。
*   **百分比:**与长度相同，但以窗口大小的百分比设置。
*   **自动:**为默认值，在浏览器确定块大小时使用。
*   **初始值:**用于将内嵌属性的值设置为默认值。
*   **inherit:** 当需要元素继承其父元素的内嵌属性作为自己的属性时使用。
*   **取消设置:**用于取消设置默认内嵌。

以下示例说明了 CSS 中的**内嵌属性**:
**示例 1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | inset-inline Property</title>
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
            position: relative;
            inset-inline: 30px 50px;
            background-color: cyan;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | inset-inline Property</b>
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
![](img/6373312bc26b40aa426ce08647491a6b.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | inset-inline Property</title>
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
            inset-inline: 30px 50px;
            background-color: cyan;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | inset-inline Property</b>
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
![](img/39ad1239bebd2bc68538533509d1e01f.png)

**支持的浏览器:****内嵌属性**支持的浏览器如下:

*   火狐浏览器
*   边缘
*   歌剧