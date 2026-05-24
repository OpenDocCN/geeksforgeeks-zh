# HTML | DOM 样式边框样式属性

> 原文:[https://www . geeksforgeeks . org/html-DOM-style-borderrightstyle-property/](https://www.geeksforgeeks.org/html-dom-style-borderrightstyle-property/)

HTML DOM 中的**样式边框样式属性**用于设置或返回元素右边框的样式。

**语法:**

*   它返回 borderRightStyle 属性。

    ```html
    object.style.borderRightStyle
    ```

*   它用于设置 borderRightStyle 属性。

    ```html
    object.style.borderRightStyle="none|hidden|dotted|dashed|solid|
    double|groove|ridge|inset|outset|initial|inherit"
    ```

**返回值:**表示元素右边框样式的字符串。

**属性值:**

| 价值 | 影响 |
| --- | --- |
| 没有人 | 没有创建边框。这是默认值。 |
| 隐藏的 | 它与' none '属性相同，只是它在表元素的边界冲突解决过程中有所帮助。 |
| 有点的 | 它使用虚线作为边框。 |
| 虚线 | 虚线用作边框。 |
| 固体 | 一条实线用作边框。 |
| 两倍 | 两条线用作边框。 |
| 律动 | 将显示三维凹槽边框。效果取决于边框颜色值。 |
| 山脉 | 将显示三维脊状边框。效果取决于边框颜色值。 |
| 插入物 | 将显示三维插入边框。效果取决于边框颜色值。 |
| 开始 | 将显示三维起始边框。效果取决于边框颜色值。 |
| 最初的 | 它将属性设置为默认值。 |
| 继承 | 它从其父元素将属性设置为。 |

所有属性值示例如下:
**示例 1:** 本示例不使用属性值。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Style borderRightStyle Property
    </title>

    <style>
        .item {
            padding: 10px;
            border: 15px solid green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style borderRightStyle Property</b>

    <p class="item">
        GeeksforGeeks is a computer science 
        portal with a huge variety of well 
        written and explained computer science 
        and programming articles, quizzes and 
        interview questions.
    </p>

    <button onclick="changeBorderStyle()">
        Change style
    </button>

    <!-- Script to uses DOM Style borderRightStyle
        Property -->
    <script>
        function changeBorderStyle() {
            elem = document.querySelector('.item');

            // Set the border style
            elem.style.borderRightStyle = 'none';
        }
    </script>
</body>

</html>                    
```

**输出:**
**点击按钮前:**
![none-before](img/3cb89fae3736752cbeda4ae37ab5790e.png)
**点击按钮后:**
![none-after](img/fbeb2ff1b90b1088fa0c744419dce072.png)

**示例 2:** 本示例使用隐藏属性值。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Style borderRightStyle Property
    </title>

    <style>
        .item {
            padding: 10px;
            border: 15px solid green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style borderRightStyle Property</b>

    <p class="item">
        GeeksforGeeks is a computer science 
        portal with a huge variety of well 
        written and explained computer science 
        and programming articles, quizzes and 
        interview questions.
    </p>

    <button onclick="changeBorderStyle()">
        Change style
    </button>

    <!-- Script to uses DOM Style borderRightStyle
        Property -->
    <script>
        function changeBorderStyle() {
            elem = document.querySelector('.item');

            // Set the border style
            elem.style.borderRightStyle = 'hidden';
        }
    </script>
</body>

</html>                    
```

**输出:**
**点击按钮前:**
![hidden-before](img/9d14067ca2bcf532cebf3ab0feefff80.png)
**点击按钮后:**
![hidden-after](img/58d033af09f9bcbf50a7f2d29e51613e.png)

**示例 3:** 本示例使用虚线属性值。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Style borderRightStyle Property
    </title>

    <style>
        .item {
            padding: 10px;
            border: 15px solid green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style borderRightStyle Property</b>

    <p class="item">
        GeeksforGeeks is a computer science 
        portal with a huge variety of well 
        written and explained computer science 
        and programming articles, quizzes and 
        interview questions.
    </p>

    <button onclick="changeBorderStyle()">
        Change style
    </button>

    <!-- Script to uses DOM Style borderRightStyle
        Property -->
    <script>
        function changeBorderStyle() {
            elem = document.querySelector('.item');

            // Set the border style
            elem.style.borderRightStyle = 'dotted';
        }
    </script>
</body>

</html>                    
```

**输出:**
**点击按钮前:**
![dotted-before](img/f05aedd8f6d6443da809a9069cca63d2.png)
**点击按钮后:**
![dotted-after](img/16485726f155d38c6d68abdf5668b671.png)

**示例 4:** 本示例使用虚线属性值。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Style borderRightStyle Property
    </title>

    <style>
        .item {
            padding: 10px;
            border: 15px solid green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style borderRightStyle Property</b>

    <p class="item">
        GeeksforGeeks is a computer science 
        portal with a huge variety of well 
        written and explained computer science 
        and programming articles, quizzes and 
        interview questions.
    </p>

    <button onclick="changeBorderStyle()">
        Change style
    </button>

    <!-- Script to uses DOM Style borderRightStyle
        Property -->
    <script>
        function changeBorderStyle() {
            elem = document.querySelector('.item');

            // Set the border style
            elem.style.borderRightStyle = 'dashed';
        }
    </script>
</body>

</html>                    
```

**输出:**
**点击按钮前:**
![dashed-before](img/4b842f2d62a8661a4761fd5bfde310d9.png)
**点击按钮后:**
![dashed-after](img/de886a2d48bdeed88eaf2266f3159a7b.png)

**示例 5:** 本示例使用实体属性值。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Style borderRightStyle Property
    </title>

    <style>
        .item {
            padding: 10px;
            border: 15px dotted green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style borderRightStyle Property</b>

    <p class="item">
        GeeksforGeeks is a computer science 
        portal with a huge variety of well 
        written and explained computer science 
        and programming articles, quizzes and 
        interview questions.
    </p>

    <button onclick="changeBorderStyle()">
        Change style
    </button>

    <!-- Script to uses DOM Style borderRightStyle
        Property -->
    <script>
        function changeBorderStyle() {
            elem = document.querySelector('.item');

            // Set the border style
            elem.style.borderRightStyle = 'solid';
        }
    </script>
</body>

</html>                    
```

**输出:**
**点击按钮前:**
![solid-before](img/5658e9e9a581e199833104ddfbdc7411.png)
**点击按钮后:**
![solid-after](img/583a1ef828a9ee7bf414d136ba041da4.png)

**示例 6:** 本示例使用双属性值。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Style borderRightStyle Property
    </title>

    <style>
        .item {
            padding: 10px;
            border: 15px solid green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style borderRightStyle Property</b>

    <p class="item">
        GeeksforGeeks is a computer science 
        portal with a huge variety of well 
        written and explained computer science 
        and programming articles, quizzes and 
        interview questions.
    </p>

    <button onclick="changeBorderStyle()">
        Change style
    </button>

    <!-- Script to uses DOM Style borderRightStyle
        Property -->
    <script>
        function changeBorderStyle() {
            elem = document.querySelector('.item');

            // Set the border style
            elem.style.borderRightStyle = 'double';
        }
    </script>
</body>

</html>                    
```

**输出:**
**点击按钮前:**
![double-before](img/c378e40274b694a10e93a545f3b42b98.png)
**点击按钮后:**
![double-after](img/c13ab48ef285d96d90e5470c12001a01.png)

**示例 7:** 本示例使用凹槽属性值。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Style borderRightStyle Property
    </title>

    <style>
        .item {
            padding: 10px;
            border: 15px solid green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style borderRightStyle Property</b>

    <p class="item">
        GeeksforGeeks is a computer science 
        portal with a huge variety of well 
        written and explained computer science 
        and programming articles, quizzes and 
        interview questions.
    </p>

    <button onclick="changeBorderStyle()">
        Change style
    </button>

    <!-- Script to uses DOM Style borderRightStyle
        Property -->
    <script>
        function changeBorderStyle() {
            elem = document.querySelector('.item');

            // Set the border style
            elem.style.borderRightStyle = 'groove';
        }
    </script>
</body>

</html>                    
```

**输出:**
**点击按钮前:**
![groove-before](img/17ae6bab4dac90ccb0cd91e6a6c9efb7.png)
**点击按钮后:**
![groove-after](img/0a7169c7b1e0c0648ec2c675c55f72c3.png)

**示例 8:** 本示例使用脊线属性值。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Style borderRightStyle Property
    </title>

    <style>
        .item {
            padding: 10px;
            border: 15px solid green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style borderRightStyle Property</b>

    <p class="item">
        GeeksforGeeks is a computer science 
        portal with a huge variety of well 
        written and explained computer science 
        and programming articles, quizzes and 
        interview questions.
    </p>

    <button onclick="changeBorderStyle()">
        Change style
    </button>

    <!-- Script to uses DOM Style borderRightStyle
        Property -->
    <script>
        function changeBorderStyle() {
            elem = document.querySelector('.item');

            // Set the border style
            elem.style.borderRightStyle = 'ridge';
        }
    </script>
</body>

</html>                    
```

**输出:**
**点击按钮前:**
![ridge-before](img/595e7b74bc5a97cdb45a1885d84478c3.png)
**点击按钮后:**
![ridge-after](img/f6875b5861387a95b49f68bef8c4328d.png)

**示例 9:** 本示例使用插图属性值。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Style borderRightStyle Property
    </title>

    <style>
        .item {
            padding: 10px;
            border: 15px outset green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style borderRightStyle Property</b>

    <p class="item">
        GeeksforGeeks is a computer science 
        portal with a huge variety of well 
        written and explained computer science 
        and programming articles, quizzes and 
        interview questions.
    </p>

    <button onclick="changeBorderStyle()">
        Change style
    </button>

    <!-- Script to uses DOM Style borderRightStyle
        Property -->
    <script>
        function changeBorderStyle() {
            elem = document.querySelector('.item');

            // Set the border style
            elem.style.borderRightStyle = 'inset';
        }
    </script>
</body>

</html>                    
```

**输出:**
**点击按钮前:**
![inset-before](img/29a816d8482097c78cee7b63b09c489c.png)
**点击按钮后:**
![inset-after](img/b4126b0f0c14cb90bf0af8c84e3a33ad.png)

**示例 10:** 本示例使用 start 属性值。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Style borderRightStyle Property
    </title>

    <style>
        .item {
            padding: 10px;
            border: 15px inset green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style borderRightStyle Property</b>

    <p class="item">
        GeeksforGeeks is a computer science 
        portal with a huge variety of well 
        written and explained computer science 
        and programming articles, quizzes and 
        interview questions.
    </p>

    <button onclick="changeBorderStyle()">
        Change style
    </button>

    <!-- Script to uses DOM Style borderRightStyle
        Property -->
    <script>
        function changeBorderStyle() {
            elem = document.querySelector('.item');

            // Set the border style
            elem.style.borderRightStyle = 'outset';
        }
    </script>
</body>

</html>                    
```

**输出:**
**点击按钮前:**
![outset-before](img/5466020f7b8dc58e87b8c27385048d14.png)
**点击按钮后:**
![outset-after](img/3dd12d77fd6c9b926b05a249b42c570f.png)

**示例 11:** 本示例使用初始属性值。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Style borderRightStyle Property
    </title>

    <style>
        .item {
            padding: 10px;
            border: 15px solid green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style borderRightStyle Property</b>

    <p class="item">
        GeeksforGeeks is a computer science 
        portal with a huge variety of well 
        written and explained computer science 
        and programming articles, quizzes and 
        interview questions.
    </p>

    <button onclick="changeBorderStyle()">
        Change style
    </button>

    <!-- Script to uses DOM Style borderRightStyle
        Property -->
    <script>
        function changeBorderStyle() {
            elem = document.querySelector('.item');

            // Set the border style
            elem.style.borderRightStyle = 'initial';
        }
    </script>
</body>

</html>                    
```

**输出:**
**点击按钮前:**
![initial-before](img/e438a346ef564aa7111b0f10b4eaf2fb.png)
**点击按钮后:**
![initial-after](img/46befe2fe9aabf103dc2646f16e76fdf.png)

**示例 12:** 本示例使用 inherit 属性值。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Style borderRightStyle Property
    </title>

    <style>
        #parent {
            border-right-style: dotted;
            padding: 10px;
        }
        .item {
            padding: 10px;
            border: 15px solid green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style borderRightStyle Property</b>

    <div id="parent">
        <p class="item">
            GeeksforGeeks is a computer science 
            portal with a huge variety of well 
            written and explained computer 
            science and programming articles, 
            quizzes and interview questions.
        </p>
    </div>

    <button onclick="changeBorderStyle()">
        Change style
    </button>

    <!-- Script to uses DOM Style borderRightStyle
        Property -->
    <script>
        function changeBorderStyle() {
            elem = document.querySelector('.item');

            // Set the border style
            elem.style.borderRightStyle = 'inherit';
        }
    </script>
</body>

</html>                    
```

**输出:**
**点击按钮前:**
![inherit-before](img/1102b2c659b29ef9017515b38a58ca38.png)
**点击按钮后:**
![inherit-after](img/13727fc83f4b3946d5b1e8377baecd16.png)

**支持的浏览器:**以下列出了 *DOM Style borderRightStyle 属性*支持的浏览器:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   苹果 Safari