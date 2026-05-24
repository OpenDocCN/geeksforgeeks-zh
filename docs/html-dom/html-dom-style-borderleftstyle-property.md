# HTML | DOM 样式边框样式属性

> 原文:[https://www . geesforgeks . org/html-DOM-style-bordereftstyle-property/](https://www.geeksforgeeks.org/html-dom-style-borderleftstyle-property/)

HTML DOM 中的**样式边框样式属性**用于设置或返回元素的左边框样式。

**语法:**

*   它返回 borderLeftStyle 属性。

    ```html
    object.style.borderTopStyle
    ```

*   它用于设置边框样式属性。

    ```html
    object.style.borderLeftStyle = "none|hidden|dotted|dashed|solid|
    double|groove|ridge|inset|outset|initial|inherit"
    ```

**属性值:**

| 价值 | 影响 |
| --- | --- |
| 没有人 | 没有创建边框。这是默认值。 |
| 隐藏的 | 它与' none '属性相同，只是它在表元素的边界冲突解决过程中有所帮助。 |
| 有点的 | 圆点用作边框。 |
| 虚线 | 虚线用作边框。 |
| 固体 | 一条实线用作边框。 |
| 两倍 | 两条线用作边框。 |
| 律动 | 将显示三维凹槽边框。效果取决于边框颜色值。 |
| 山脉 | 将显示三维脊状边框。效果取决于边框颜色值。 |
| 插入物 | 将显示三维插入边框。效果取决于边框颜色值。 |
| 开始 | 将显示三维起始边框。效果取决于边框颜色值。 |
| 最初的 | 它将属性设置为初始值。 |
| 继承 | 它将属性设置为从其父级继承。 |

**返回值:**返回一个字符串值，代表元素左边框的样式。

**示例 1:** 本示例不描述属性值。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Style borderLeftStyle Property
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

    <b>DOM Style borderLeftStyle Property</b>

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

    <script>
        function changeBorderStyle() {
            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderLeftStyle = 'none';
        }
    </script>
</body>

</html>                    
```

**输出:**
**点击按钮前:**
![none-before](img/c7d0f6da29568ecd206b3e13e3fca23a.png)
**点击按钮后:**
![none-after](img/d3d1103a9141e64d734244165b61f7ae.png)

**例 2:** 本例描述隐藏属性值。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Style borderLeftStyle Property
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

    <b>DOM Style borderLeftStyle Property</b>

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

    <script>
        function changeBorderStyle() {
            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderLeftStyle = 'hidden';
        }
    </script>
</body>

</html>                    
```

**输出:**
**点击按钮前:**
![hidden-before](img/1533eb33a9219b45d4719dc47dbb3cd0.png)
**点击按钮后:**
![hidden-after](img/205726ad7d758b7533c58b1e7d90bef2.png)

**示例 3:** 本示例描述了点状属性值。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Style borderLeftStyle Property
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

    <b>DOM Style borderLeftStyle Property</b>

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

    <script>
        function changeBorderStyle() {
            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderLeftStyle = 'dotted';
        }
    </script>
</body>

</html>                    
```

**输出:**
**点击按钮前:**
![dotted-before](img/2a081d2a28ff3dbe705e46e4caa05b2e.png)
**点击按钮后:**
![dotted-after](img/d77f1976dc370de2e442e67df235a1ec.png)

**示例 4:** 本示例描述了虚线属性值。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Style borderLeftStyle Property
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

    <b>DOM Style borderLeftStyle Property</b>

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

    <script>
        function changeBorderStyle() {
            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderLeftStyle = 'dashed';
        }
    </script>
</body>

</html>                    
```

**输出:**
**点击按钮前:**
![dashed-before](img/392ebd693efbf9be745f2408f932d712.png)
**点击按钮后:**
![dashed-after](img/895b4f2e6f942184f853e5a590369e3b.png)

**实施例 5:** 本实施例描述了固体属性值。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Style borderLeftStyle Property
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

    <b>DOM Style borderLeftStyle Property</b>

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

    <script>
        function changeBorderStyle() {
            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderLeftStyle = 'solid';
        }
    </script>
</body>

</html>                    
```

**输出:**
**点击按钮前:**
![solid-before](img/05e98cbd24381e21f9b92dde8e062a05.png)
**点击按钮后:**
![solid-after](img/83b592295ee8dc74a44b85437226f3a8.png)

**例 6:** 本例描述双属性值。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Style borderLeftStyle Property
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

    <b>DOM Style borderLeftStyle Property</b>

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

    <script>
        function changeBorderStyle() {
            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderLeftStyle = 'double';
        }
    </script>
</body>

</html>                    
```

**输出:**
**点击按钮前:**
![double-before](img/b4169b2daacf0ed7fd22914fccee1f16.png)
**点击按钮后:**
![double-after](img/1db5d12a9b010c3145d2daef1f1c41b5.png)

**示例 7:** 本示例描述了凹槽属性值。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Style borderLeftStyle Property
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

    <b>DOM Style borderLeftStyle Property</b>

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

    <script>
        function changeBorderStyle() {
            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderLeftStyle = 'groove';
        }
    </script>
</body>

</html>                    
```

**输出:**
**点击按钮前:**
![groove-before](img/76335ec016703dd9d445a29ab306c37d.png)
**点击按钮后:**
![groove-after](img/f8bc3213887454d826ad0105de2e37be.png)

**例 8:** 本例描述脊线属性值。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Style borderLeftStyle Property
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

    <b>DOM Style borderLeftStyle Property</b>

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

    <script>
        function changeBorderStyle() {
            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderLeftStyle = 'ridge';
        }
    </script>
</body>

</html>                    
```

**输出:**
**点击按钮前:**
![ridge-before](img/6ef654c9e1c7d46ac03017ad87a7c8a9.png)
**点击按钮后:**
![ridge-after](img/daaef93a0dee803fbddb3853d8f53a3f.png)

**示例 9:** 本示例描述了插入属性值。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Style borderLeftStyle Property
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

    <b>DOM Style borderLeftStyle Property</b>

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

    <script>
        function changeBorderStyle() {
            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderLeftStyle = 'inset';
        }
    </script>
</body>

</html>                    
```

**输出:**
**点击按钮前:**
![inset-before](img/3bddd51f14b8c3ccf233c7c247d5d494.png)
**点击按钮后:**
![inset-after](img/9d73fa8b34a7395f6ab550ed8a76f8c8.png)

**示例 10:** 本示例描述了起始属性值。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Style borderLeftStyle Property
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

    <b>DOM Style borderLeftStyle Property</b>

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

    <script>
        function changeBorderStyle() {
            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderLeftStyle = 'outset';
        }
    </script>
</body>

</html>                    
```

**输出:**
**点击按钮前:**
![outset-before](img/f3726ab1ef24334e09774cff504220cb.png)
**点击按钮后:**
![outset-after](img/af426e0d2f59f9d576ad7f34cae3cd16.png)

**例 11:** 本例描述初始属性值。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Style borderLeftStyle Property
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

    <b>DOM Style borderLeftStyle Property</b>

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

    <script>
        function changeBorderStyle() {
            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderLeftStyle = 'initial';
        }
    </script>
</body>

</html>                    
```

**输出:**
**点击按钮前:**
![initial-before](img/bacc5d88d6fcabde078e595ca625f8e8.png)
**点击按钮后:**
![initial-after](img/4b968f5bc202994cfcb6fcc3f315fda0.png)

**例 12:** 本例描述继承属性值。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Style borderLeftStyle Property
    </title>

    <style>
        #parent {
            border-left-style: dotted;
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
    <b>DOM Style borderLeftStyle Property</b>

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

    <script>
        function changeBorderStyle() {
            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderLeftStyle = 'inherit';
        }
    </script>
</body>

</html>                    
```

**输出:**
**点击按钮前:**
![inherit-before](img/dc9bd7038ca8368f549d1f78c5f13ec2.png)
**点击按钮后:**
![inherit-after](img/06857ded8f72ddbf4563a6792b50f882.png)

**支持的浏览器:**由*DOM Style bordereftstyle 属性*支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧