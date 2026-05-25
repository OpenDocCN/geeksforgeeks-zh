# HTML DOM 样式 borderTopWidth 属性

> 原文：[https://www.geeksforgeeks.org/html-dom-style-bordertopwidth-property/](https://www.geeksforgeeks.org/html-dom-style-bordertopwidth-property/)

HTML DOM 中的 `borderTopWidth` 属性用于设置或返回元素顶部边框的宽度。

## 语法

要获取 `borderTopWidth` 属性：

```html
object.style.borderTopWidth
```

要设置 `borderTopWidth` 属性：

```html
object.style.borderTopWidth = "thin | medium | thick | length | initial | inherit"
```

## 返回值

返回一个字符串值，代表元素上边框的宽度。

## 属性值

### thin
用于定义细的上边框。

**示例：**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>DOM Style BorderTopWidth</title>
    <style>
        .elem {
            border-style: solid;
            padding: 10px;
        }
    </style>
</head>
<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style BorderTopWidth</b>
    <p class="elem">
        GeeksforGeeks is a computer science portal with a huge variety of well written and explained computer science and programming articles, quizzes and interview questions.
    </p>
    <button onclick="changeWidth()">Change borderTopWidth</button>
    <!-- Script to change borderTopWidth -->
    <script>
        function changeWidth() {
            elem = document.querySelector('.elem');
            elem.style.borderTopWidth = 'thin';
        }
    </script>
</body>
</html>
```

**输出：**

**点击按钮前：**

![thin-before](img/8bf1f7e22e735918e25561cee7fdf3a0.png)

**点击按钮后：**

![thin-after](img/d205c470481f3661f35b100d584a1364.png)

### medium
用于定义中等的上边框。这是默认值。

**示例：**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>DOM Style BorderTopWidth</title>
    <style>
        .elem {
            border: thick solid;
            padding: 10px;
        }
    </style>
</head>
<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style BorderTopWidth</b>
    <p class="elem">
        GeeksforGeeks is a computer science portal with a huge variety of well written and explained computer science and programming articles, quizzes and interview questions.
    </p>
    <button onclick="changeWidth()">Change borderTopWidth</button>
    <!-- Script to change borderTopWidth -->
    <script>
        function changeWidth() {
            elem = document.querySelector('.elem');
            elem.style.borderTopWidth = 'medium';
        }
    </script>
</body>
</html>
```

**输出：**

**点击按钮前：**

![medium-before](img/eb913231ad795fd93c2d199a1b9cf5ed.png)

**点击按钮后：**

![medium-after](img/e3b853377775b193efdfd6eb15619397.png)

### thick
用于定义粗的上边框。

**示例：**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>DOM Style BorderTopWidth</title>
    <style>
        .elem {
            border-style: solid;
            padding: 10px;
        }
    </style>
</head>
<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style BorderTopWidth</b>
    <p class="elem">
        GeeksforGeeks is a computer science portal with a huge variety of well written and explained computer science and programming articles, quizzes and interview questions.
    </p>
    <button onclick="changeWidth()">Change borderTopWidth</button>
    <!-- Script to change borderTopWidth -->
    <script>
        function changeWidth() {
            elem = document.querySelector('.elem');
            elem.style.borderTopWidth = 'thick';
        }
    </script>
</body>
</html>
```

**输出：**

**点击按钮前：**

![thick-before](img/16afb8b09d4c16e41d11c20ebbd8ee95.png)

**点击按钮后：**

![thick-after](img/b821ac85959f30c1dc082c33ea589cdf.png)

### length
用于以长度单位定义上边框的宽度。

**示例：**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>DOM Style BorderTopWidth</title>
    <style>
        .elem {
            border-style: solid;
            padding: 10px;
        }
    </style>
</head>
<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style BorderTopWidth</b>
    <p class="elem">
        GeeksforGeeks is a computer science portal with a huge variety of well written and explained computer science and programming articles, quizzes and interview questions.
    </p>
    <button onclick="changeWidth()">Change borderTopWidth</button>
    <!-- Script to change borderTopWidth -->
    <script>
        function changeWidth() {
            elem = document.querySelector('.elem');
            elem.style.borderTopWidth = '10px';
        }
    </script>
</body>
</html>
```

**输出：**

**点击按钮前：**

![length-before](img/2d1a7574e2f8f4c842202c7af4273d84.png)

**点击按钮后：**

![length-after](img/33f24937c756598df930a5147e66cd2a.png)

### initial
用于将此属性设置为其默认值。

**示例：**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>DOM Style BorderTopWidth</title>
    <style>
        .elem {
            border-style: solid;
            padding: 10px;
            border-top-width: 2px;
        }
    </style>
</head>
<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style BorderTopWidth</b>
    <p class="elem">
        GeeksforGeeks is a computer science portal with a huge variety of well written and explained computer science and programming articles, quizzes and interview questions.
    </p>
    <button onclick="changeWidth()">Change borderTopWidth</button>
    <!-- Script to change borderTopWidth -->
    <script>
        function changeWidth() {
            elem = document.querySelector('.elem');
            elem.style.borderTopWidth = 'initial';
        }
    </script>
</body>
</html>
```

**输出：**

**点击按钮前：**

![initial-before](img/85f3e6a43b1113f5fde2b15d7b7ec073.png)

**点击按钮后：**

![initial-after](img/445c672dd90a4deed82cacad8816c8d1.png)

### inherit
从其父元素继承该属性。

**示例：**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>DOM Style BorderTopWidth</title>
    <style>
        #parent {
            padding: 10px;
            border-style: solid;
            /* Setting the borderTopWidth of the parent */
            border-top-width: 15px;
        }
        .elem {
            border-style: solid;
            padding: 10px;
        }
    </style>
</head>
```

# GeeksforGeeks
## DOM Style BorderTopWidth

```html
<body>
    <h1 style="color: green">
        GeeksforGeeks
    </h1>
    <b>
        DOM Style BorderTopWidth
    </b>
    <br>
    <br>
    <div id="parent">
        <p class="elem">
            GeeksforGeeks is a computer science portal with a huge variety of well written and explained computer science and programming articles, quizzes and interview questions.
        </p>
    </div>
    <br>
    <button onclick="changeWidth()">
        Change borderTopWidth
    </button>

    <!-- Script to change borderTopWidth -->
    <script>
        function changeWidth() {
            elem = document.querySelector('.elem');
            elem.style.borderTopWidth = 'inherit';
        }
    </script>
</body>
</html>
```

## 输出

### 点击按钮前

![inherit-before](img/ed90a24cff9a35a2378ff67d5d01a592.png)

### 点击按钮后

![inherit-after](img/50ae24bd6f104dd7401d1df2aaa654c2.png)

## 支持的浏览器

由`borderTopWidth`属性支持的浏览器如下：

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   苹果 Safari