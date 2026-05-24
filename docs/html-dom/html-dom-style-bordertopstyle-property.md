# HTML | DOM 样式边框样式属性

> 原文:[https://www . geeksforgeeks . org/html-DOM-style-bordertopstyle-property/](https://www.geeksforgeeks.org/html-dom-style-bordertopstyle-property/)

DOM Style **borderTopStyle** 属性用于**设置**或**返回**元素的顶部边框样式。

**语法:**

*   获取 borderTopStyleProperty

    ```html
    object.style.borderTopStyle
    ```

*   要设置 borderTopStyleProperty

    ```html
    object.style.borderTopStyle = "none | hidden | dotted | dashed |
    solid | double | groove |ridge | inset | outset | initial | 
    inherit"
    ```

**返回值:**返回一个字符串值，代表元素上边框的样式。

**属性值:**

| 价值 | 影响 |
| --- | --- |
| 没有人 | 没有创建边框。这是默认值。 |
| 隐藏的 | 视觉上与“无”相同，只是它在表格元素的边界冲突解决过程中有所帮助。 |
| 有点的 | 圆点用作边框。 |
| 虚线 | 虚线用作边框。 |
| 固体 | 一条实线用作边框。 |
| 两倍 | 两条线用作边框。 |
| 律动 | 将显示三维凹槽边框。效果取决于边框颜色值。 |
| 山脉 | 将显示三维脊状边框。效果取决于边框颜色值。 |
| 插入物 | 将显示三维插入边框。效果取决于边框颜色值。 |
| 开始 | 将显示三维起始边框。效果取决于边框颜色值。 |
| 最初的 | 将属性设置为其初始值。 |
| 继承 | 设置从其父级继承的属性。 |

这些值通过以下示例进行了演示:

**示例-1:** 使用 none 值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>
        DOM Style borderTopStyle Property
    </title>
    <style>
        .item {
            height: 50px;
            padding: 10px;
            border: 15px solid green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">
      GeeksforGeeks
    </h1>
    <b>DOM Style borderTopStyle Property</b>
    <p>Click on the button to change the 
      style of the border on the top</p>

    <div class="item">
      GeeksforGeeks
    </div>

    <button onclick="changeBorderTopStyle()">
      Change style
    </button>

    <script>
        function changeBorderTopStyle() {
            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderTopStyle = 'none';
        }
    </script>
</body>

</html>
```

**输出:**

**点击按钮前:**
![none-before](img/ee063f9103d1d54034ab64d9734f88bd.png)

**点击按钮后:**
![none-after](img/b31d04e7707033563b3166923084e457.png)

**示例-2:** 使用隐藏值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>
        DOM Style borderTopStyle Property
    </title>
    <style>
        .item {
            height: 50px;
            padding: 10px;
            border: 15px solid green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style borderTopStyle Property</b>
    <p>Click on the button to change the
      style of the border on the top</p>
    <div class="item">GeeksforGeeks</div> 

    <button onclick="changeBorderTopStyle()">
      Change style
    </button>

    <script>
        function changeBorderTopStyle() {
            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderTopStyle = 'hidden';
        }
    </script>
</body>

</html>
```

**输出:**

**点击按钮前:**

![none-before](img/ee063f9103d1d54034ab64d9734f88bd.png)

**点击按钮后:**

![hidden-after](img/239d70012b3bd2fc0b3fc6f6daf1bc44.png)

**示例-3:** 使用虚线值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>
        DOM Style borderTopStyle Property
    </title>
    <style>
        .item {
            height: 50px;
            padding: 10px;
            border: 15px solid green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style borderTopStyle Property</b>
    <p>Click on the button to change the 
      style of the border on the top</p>

    <div class="item">GeeksforGeeks</div>
    <button onclick="changeBorderTopStyle()">
      Change style
    </button>

    <script>
        function changeBorderTopStyle() {
            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderTopStyle = 'dotted';
        }
    </script>
</body>

</html>
```

**输出:**

**点击按钮前:**

![none-before](img/ee063f9103d1d54034ab64d9734f88bd.png)

**点击按钮后:**

![dotted-after](img/1d499bb48dfa31b2c8ed7dfd8595c999.png)

**示例-4:** 使用虚线值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>
        DOM Style borderTopStyle Property
    </title>
    <style>
        .item {
            height: 50px;
            padding: 10px;
            border: 15px solid green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style borderTopStyle Property</b>
    <p>Click on the button to change the
      style of the border on the top</p>
    <div class="item">GeeksforGeeks</div>
    <button onclick="changeBorderTopStyle()">
      Change style
    </button>

    <script>
        function changeBorderTopStyle() {
            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderTopStyle = 'dashed';
        }
    </script>
</body>

</html>
```

**输出:**

**点击按钮前:**

![none-before](img/ee063f9103d1d54034ab64d9734f88bd.png)

**点击按钮后:**

![dashed-after](img/bbb90520250d799a8a8d0fc4fb1eb77b.png)

**示例-5:** 使用实线值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>
        DOM Style borderTopStyle Property
    </title>
    <style>
        .item {
            height: 50px;
            padding: 10px;
            border: 15px dotted green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style borderTopStyle Property</b>
    <p>Click on the button to change the 
      style of the border on the top</p>
    <div class="item">GeeksforGeeks</div>
    <button onclick="changeBorderTopStyle()">
      Change style
    </button>

    <script>
        function changeBorderTopStyle() {
            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderTopStyle = 'solid';
        }
    </script>
</body>

</html>
```

**输出:**

**点击按钮前:**

![solid-before](img/1d830d30bab1514d8e04ad2b0cda7bbf.png)

**点击按钮后:**

![solid-after](img/f6c59f99c10442f1548db423b2061e79.png)

**示例-6:** 使用双精度值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>
        DOM Style borderTopStyle Property
    </title>
    <style>
        .item {
            height: 50px;
            padding: 10px;
            border: 15px solid green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style borderTopStyle Property</b>
    <p>Click on the button to change the style
      of the border on the top</p>
    <div class="item">GeeksforGeeks</div>

    <button onclick="changeBorderTopStyle()">
      Change style
    </button>

    <script>
        function changeBorderTopStyle() {
            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderTopStyle = 'double';
        }
    </script>
</body>

</html>
```

**输出:**

**点击按钮前:**

![none-before](img/ee063f9103d1d54034ab64d9734f88bd.png)

**点击按钮后:**

![double-after](img/0a107a94b598e5edcc8040a822f8b783.png)

**示例-7:** 使用凹槽值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>
        DOM Style borderTopStyle Property
    </title>
    <style>
        .item {
            height: 50px;
            padding: 10px;
            border: 15px solid green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style borderTopStyle Property</b>
    <p>Click on the button to change the style
      of the border on the top</p>
    <div class="item">GeeksforGeeks</div>

    <button onclick="changeBorderTopStyle()">
      Change style
    </button>

    <script>
        function changeBorderTopStyle() {
            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderTopStyle = 'groove';
        }
    </script>
</body>

</html>
```

**输出:**

**点击按钮前:**

![none-before](img/ee063f9103d1d54034ab64d9734f88bd.png)

**点击按钮后:**

![groove-after](img/959d8467dd4c235073885f4815f8a21b.png)

**示例-8:** 使用脊线值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>
        DOM Style borderTopStyle Property
    </title>
    <style>
        .item {
            height: 50px;
            padding: 10px;
            border: 15px solid green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style borderTopStyle Property</b>
    <p>Click on the button to change the style 
      of the border on the top</p>
    <div class="item">GeeksforGeeks</div>

    <button onclick="changeBorderTopStyle()">
      Change style
    </button>

    <script>
        function changeBorderTopStyle() {
            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderTopStyle = 'ridge';
        }
    </script>
</body>

</html>
```

**输出:**

**点击按钮前:**

![none-before](img/ee063f9103d1d54034ab64d9734f88bd.png)

**点击按钮后:**

![ridge-after](img/a74f458e838126f01ef20f13dee88617.png)

**示例-9:** 使用插入值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>
        DOM Style borderTopStyle Property
    </title>
    <style>
        .item {
            height: 50px;
            padding: 10px;
            border: 15px solid green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style borderTopStyle Property</b>
    <p>Click on the button to change the style
      of the border on the top</p>
    <div class="item">GeeksforGeeks</div>

    <button onclick="changeBorderTopStyle()">
      Change style
    </button>

    <script>
        function changeBorderTopStyle() {
            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderTopStyle = 'inset';
        }
    </script>
</body>

</html>
```

**输出:**

**点击按钮前:**

![none-before](img/ee063f9103d1d54034ab64d9734f88bd.png)

**点击按钮后:**

![inset-after](img/7ec261007c51ae29de3127e5507439e3.png)

**示例-10:** 使用起始值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>
        DOM Style borderTopStyle Property
    </title>
    <style>
        .item {
            height: 50px;
            padding: 10px;
            border: 15px inset green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style borderTopStyle Property</b>
    <p>Click on the button to change the style
      of the border on the top</p>
    <div class="item">GeeksforGeeks</div>

    <button onclick="changeBorderTopStyle()">
      Change style
    </button>

    <script>
        function changeBorderTopStyle() {
            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderTopStyle = 'outset';
        }
    </script>
</body>

</html>
```

**输出:**

**点击按钮前:**

![outset-before](img/434000876950b9d5fb2840784dfbc16d.png)

**点击按钮后:**

![outset-after](img/f57df80812f9f131a1f185b8fbd00aee.png)

**示例-11:** 使用初始值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>
        DOM Style borderTopStyle Property
    </title>
    <style>
        .item {
            height: 50px;
            padding: 10px;
            border: 15px solid green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style borderTopStyle Property</b>
    <p>Click on the button to change the style
      of the border on the top</p>
    <div class="item">GeeksforGeeks</div>

    <button onclick="changeBorderTopStyle()">
      Change style
    </button>

    <script>
        function changeBorderTopStyle() {
            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderTopStyle = 'initial';
        }
    </script>
</body>

</html>
```

**输出:**

**点击按钮前:**

![none-before](img/ee063f9103d1d54034ab64d9734f88bd.png)

**点击按钮后:**

![initial-after](img/41dd52b81d6351dc1bc1019b8c4fac5d.png)

**示例-12:** 使用继承值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>
        DOM Style borderTopStyle Property
    </title>
    <style>
        #parent {
            border-top-style: dotted;
            padding: 10px;
        }

        .item {
            height: 50px;
            padding: 10px;
            border: 15px solid green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style borderTopStyle Property</b>
    <p>Click on the button to change the style
      of the border on the top</p>
    <div id="parent">
        <div class="item">GeeksforGeeks</div>
    </div>

    <button onclick="changeBorderTopStyle()">
      Change style
    </button>

    <script>
        function changeBorderTopStyle() {
            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderTopStyle = 'inherit';
        }
    </script>
</body>

</html>
```

**输出:**

**点击按钮前:**

![inherit-before](img/fd1fa9fd2dd7c1226d9b6fa498e9897e.png)

**点击按钮后:**

![inherit-after](img/9237ba71af5591b6ee031245f7438e40.png)

**支持的浏览器:**由 *borderTopStyle* 属性支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   苹果 Safari