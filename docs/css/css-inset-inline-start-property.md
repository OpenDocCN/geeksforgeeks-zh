# CSS |嵌入-内嵌-开始属性

> 原文:[https://www . geesforgeks . org/CSS-inset-inline-start-property/](https://www.geeksforgeeks.org/css-inset-inline-start-property/)

CSS 中的**内嵌开始属性**用于定义逻辑内嵌开始偏移量，而不是块偏移量或逻辑块。此属性可以应用于任何写入模式属性。

**语法:**

```html
inset-inline-start: length|percentage|auto|inherit|initial|unset;
```

**属性值:**

*   **长度:**设置 px、cm、pt 等定义的固定值。允许负值。它的默认值是 0px。
*   **百分比:**与窗口大小百分比设置的长度相同。
*   **自动:**当希望浏览器确定块大小时使用。
*   **初始值:**用于将 inset-inline-start 属性的值设置为默认值。
*   **inherit:** 当需要元素从其父元素继承 inset-inline-start 属性时使用。
*   **取消设置:**用于取消设置默认内嵌开始。

下面的例子说明了 CSS 中的**内嵌开始属性**:

**例 1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | inset-inline-start Property</title>
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
            inset-inline-start: 10px;
            background-color: cyan;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | inset-inline-start Property</b>
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
![](img/8bdf37d0097aa82fedfff98e03a8e2ec.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | inset-inline-start Property</title>
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
            inset-inline-start: 50px;
            background-color: cyan;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | inset-inline-start Property</b>
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
![](img/71ff7d6f839933ce8e9e04de92377a5e.png)

**支持的浏览器:****内嵌开始属性**支持的浏览器如下:

*   火狐浏览器
*   边缘
*   歌剧