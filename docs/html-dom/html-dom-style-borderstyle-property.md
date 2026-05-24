# HTML | DOM 样式边框样式属性

> 原文:[https://www . geesforgeks . org/html-DOM-style-border style-property/](https://www.geeksforgeeks.org/html-dom-style-borderstyle-property/)

DOM Style **边框样式**属性用于**设置**或**返回** *元素的边框样式*。

**语法:**

*   要获得边框样式

    ```html
    object.style.borderStyle
    ```

*   设置边框样式

    ```html
    object.style.borderStyle = "none | hidden | dotted | dashed | 
    solid | double | groove | ridge | inset | outset | initial |
    inherit"
    ```

**返回值:**返回一个字符串值，代表元素边框的样式。

**属性值:**各属性值同例。

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
      DOM Style borderStyle Property
    </title>
    <style>
        .item {
            padding: 10px;
            border: 15px solid green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">
      GeeksforGeeks
    </h1>
    <b>
      DOM Style borderStyle Property
    </b>
    <p class="item">
        GeeksforGeeks is a computer science 
      portal with a huge variety of well written
      and explained computer science and
      programming articles, quizzes and
      interview questions.
    </p>
    <button onclick="changeBorderStyle()">
      Change style
    </button>

    <script>
        function changeBorderStyle() {

            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderStyle = 'none';
        }
    </script>
</body>

</html>
```

**输出:**
**点击按钮前:**
![none-before](img/227d93d7ad967062904a534c76cb4af0.png)

**点击按钮后:**
![none-after](img/24f0a84e336d894a7f10886eb5d321da.png)

**示例-2:** 使用隐藏值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>
      DOM Style borderStyle Property
    </title>
    <style>
        .item {
            padding: 10px;
            border: 15px solid green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">
      GeeksforGeeks
    </h1>
    <b>
      DOM Style borderStyle Property
    </b>
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
            elem.style.borderStyle = 'hidden';
        }
    </script>
</body>

</html>
```

**输出:**
**点击按钮前:**
![hidden-before](img/196780104143904d42cc075cf0b42323.png)

**点击按钮后:**
![hidden-after](img/266079431e1e9fbbc0dc4439a8e2ab58.png)

**示例-3:** 使用虚线值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>
      DOM Style borderStyle Property
    </title>
    <style>
        .item {
            padding: 10px;
            border: 15px solid green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">
      GeeksforGeeks
    </h1>
    <b>
      DOM Style borderStyle Property
    </b>
    <p class="item">
      GeeksforGeeks is a computer science
      portal with a huge variety of well 
      written and explained computer science
      and programming articles, quizzes 
      and interview questions.
    </p>
    <button onclick="changeBorderStyle()">
      Change style
    </button>

    <script>
        function changeBorderStyle() {
            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderStyle = 'dotted';
        }
    </script>
</body>

</html>
```

**输出:**

**点击按钮前:**
![dotted-before](img/286a0d3d21d1af33b4e4658449005018.png)

**点击按钮后:**
![dotted-after](img/f171191e5fa230842b95717024cb0a17.png)

**示例-4:** 使用虚线值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>
      DOM Style borderStyle Property
    </title>
    <style>
        .item {
            padding: 10px;
            border: 15px solid green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">
      GeeksforGeeks
    </h1>
    <b>
      DOM Style borderStyle Property
    </b>
    <p class="item">
      GeeksforGeeks is a computer science 
      portal with a huge variety of well 
      written and explained computer 
      science and programming articles, 
      quizzes and interview questions.
    </p>
    <button onclick="changeBorderStyle()">
      Change style
    </button>

    <script>
        function changeBorderStyle() {
            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderStyle = 'dashed';
        }
    </script>
</body>

</html>
```

**输出:**
**点击按钮前:**
![dashed-before](img/ca39f426e8039da7b29ac950fb781053.png)

**点击按钮后:**

![dashed-after](img/1887db7f3e1bf9a53896e129c98e8178.png)

**示例-5:** 使用实线值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>
      DOM Style borderStyle Property
    </title>
    <style>
        .item {
            padding: 10px;
            border: 15px dotted green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">
      GeeksforGeeks
    </h1>
    <b>
      DOM Style borderStyle Property
    </b>
    <p class="item">
      GeeksforGeeks is a computer science portal
      with a huge variety of well written and
      explained computer science and programming
      articles, quizzes and interview questions.
    </p>
    <button onclick="changeBorderStyle()">
      Change style
    </button>

    <script>
        function changeBorderStyle() {
            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderStyle = 'solid';
        }
    </script>
</body>

</html>
```

**输出:**
**点击按钮前:**
![solid-before](img/f22225913ba5d4fbc1471a1d53c72b97.png)

**点击按钮后:**

![solid-after](img/5c65373dda0375e66d45bb86a259f4f2.png)

**示例-6:** 使用双精度值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>
      DOM Style borderStyle Property
    </title>
    <style>
        .item {
            padding: 10px;
            border: 15px solid green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">
      GeeksforGeeks
    </h1>
    <b>
      DOM Style borderStyle Property
    </b>
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
            elem.style.borderStyle = 'double';
        }
    </script>
</body>

</html>
```

**输出:**

**点击按钮前:**

![double-before](img/8936ef4aa4b319d6b1049633f5322b08.png)

**点击按钮后:**

![double-after](img/b3ee726c1acaaecad32a0eb9e21364fb.png)

**示例-7:** 使用凹槽值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>
      DOM Style borderStyle Property
    </title>
    <style>
        .item {
            padding: 10px;
            border: 15px solid green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">
      GeeksforGeeks
    </h1>
    <b>
      DOM Style borderStyle Property
    </b>
    <p class="item">
      GeeksforGeeks is a computer science portal
      with a huge variety of well written and 
      explained computer science and programming
      articles, quizzes and interview questions.
    </p>
    <button onclick="changeBorderStyle()">
      Change style
    </button>

    <script>
        function changeBorderStyle() {
            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderStyle = 'groove';
        }
    </script>
</body>

</html>
```

**输出:**

**点击按钮前:**
![groove-before](img/1182c7bb2907eeea3befea01bdc3993c.png)

**点击按钮后:**

![groove-after](img/babe5a59e49c2e7c590f0613a6cf11ab.png)

**示例-8:** 使用脊线值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>
      DOM Style borderStyle Property
    </title>
    <style>
        .item {
            padding: 10px;
            border: 15px solid green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">
      GeeksforGeeks
    </h1>
    <b>
      DOM Style borderStyle Property
  </b>
    <p class="item"> 
      GeeksforGeeks is a computer science 
      portal with a huge variety of well 
      written and explained computer science
      and programming articles, quizzes 
      and interview questions.
    </p>
    <button onclick="changeBorderStyle()">
      Change style
    </button>

    <script>
        function changeBorderStyle() {
            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderStyle = 'ridge';
        }
    </script>
</body>

</html>
```

**输出:**

**点击按钮前:**

![ridge-before](img/331fe21e1beee49e7983d8896cea1e20.png)

**点击按钮后:**

![ridge-after](img/d1a99cb67d800cae5d99f0cad7e8ad6e.png)

**示例-9:** 使用插入值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>
        DOM Style borderStyle Property
    </title>
    <style>
        .item {
            padding: 10px;
            border: 15px solid green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">
      GeeksforGeeks
    </h1>
    <b>
      DOM Style borderStyle Property
    </b>
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
            elem.style.borderStyle = 'inset';
        }
    </script>
</body>

</html>
```

**输出:**

**点击按钮前:**

![inset-before](img/51c18313b9088f208df68434584243ee.png)

**点击按钮后:**

![inset-after](img/844be4e797e039394167d3663cfc0c3b.png)

**示例-10:** 使用起始值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>
      DOM Style borderStyle Property
    </title>
    <style>
        .item {
            padding: 10px;
            border: 15px inset green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">
      GeeksforGeeks
    </h1>
    <b>
      DOM Style borderStyle Property
    </b>
    <p class="item">  
      GeeksforGeeks is a computer science portal
      with a huge variety of well written and 
      explained computer science and programming
      articles, quizzes and interview questions.
    </p>
    <button onclick="changeBorderStyle()">
      Change style
    </button>

    <script>
        function changeBorderStyle() {
            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderStyle = 'outset';
        }
    </script>
</body>

</html>
```

**输出:**

**点击按钮前:**

![outset-before](img/f0e7a1536fe4323f1a25757aff85fbb5.png)

**点击按钮后:**

![outset-after](img/b0a026ef78bcce8fc22ed115c0387630.png)

**示例-11:** 使用初始值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>
      DOM Style borderStyle Property
    </title>
    <style>
        .item {
            padding: 10px;
            border: 15px solid green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">
      GeeksforGeeks
    </h1>
    <b>
      DOM Style borderStyle Property
    </b>
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
            elem.style.borderStyle = 'initial';
        }
    </script>
</body>

</html>
```

**输出:**

**点击按钮前:**

![initial-before](img/0c3754dcc859362e4d1b7b749175b371.png)

**点击按钮后:**

![initial-after](img/e3368670348ffa9778f8600e92ae7630.png)

**示例-12:** 使用继承值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>
      DOM Style borderStyle Property
    </title>
    <style>
        #parent {
            border-style: dotted;
            padding: 10px;
        }

        .item {
            padding: 10px;
            border: 15px solid green;
        }
    </style>
</head>

<body>
    <h1 style="color: green">
      GeeksforGeeks
    </h1>
    <b>
      DOM Style borderStyle Property
    </b>

    <div id="parent">
        <p class="item"> 
          GeeksforGeeks is a computer science portal
          with a huge variety of well written and 
          explained computer science and programming
          articles, quizzes and interview questions.
        </p>
    </div>

    <button onclick="changeBorderStyle()">
      Change style
    </button>

    <script>
        function changeBorderStyle() {
            elem = document.querySelector('.item');

            // Setting the border style
            elem.style.borderStyle = 'inherit';
        }
    </script>
</body>

</html>
```

**输出:**

**点击按钮前:**

![inherit-before](img/8e65c3582f20005e971d25a351b189a2.png)

**点击按钮后:**

![inherit-after](img/aed14fd870deee13ded7442e2b4c367e.png)

**支持的浏览器:**由 *borderStyle* 属性支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   苹果 Safari