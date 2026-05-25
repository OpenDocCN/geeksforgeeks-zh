# HTML DOM Style borderTopStyle 属性

> 原文：[https://www.geeksforgeeks.org/html-dom-style-bordertopstyle-property/](https://www.geeksforgeeks.org/html-dom-style-bordertopstyle-property/)

DOM Style `borderTopStyle` 属性用于设置或返回元素的顶部边框样式。

## 语法

获取 `borderTopStyle` 属性：
```html
object.style.borderTopStyle
```

设置 `borderTopStyle` 属性：
```html
object.style.borderTopStyle = "none | hidden | dotted | dashed | solid | double | groove | ridge | inset | outset | initial | inherit"
```

## 返回值

返回一个字符串值，代表元素上边框的样式。

## 属性值

| 值 | 描述 |
| --- | --- |
| `none` | 无边框。这是默认值。 |
| `hidden` | 与 `none` 相同，但在表格元素的边界冲突解决过程中有帮助。 |
| `dotted` | 点状边框。 |
| `dashed` | 虚线边框。 |
| `solid` | 实线边框。 |
| `double` | 双线边框。 |
| `groove` | 3D 凹槽边框。效果取决于 `border-color` 值。 |
| `ridge` | 3D 脊状边框。效果取决于 `border-color` 值。 |
| `inset` | 3D 内嵌边框。效果取决于 `border-color` 值。 |
| `outset` | 3D 外凸边框。效果取决于 `border-color` 值。 |
| `initial` | 将属性设置为其默认值。 |
| `inherit` | 从父元素继承该属性。 |

这些值通过以下示例进行了演示：

## 示例-1：使用 `none` 值

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>DOM Style borderTopStyle Property</title>
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
    <p>Click on the button to change the style of the border on the top</p>
    <div class="item">GeeksforGeeks</div>
    <button onclick="changeBorderTopStyle()">Change style</button>
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

**输出：**

**点击按钮前：**
![none-before](img/ee063f9103d1d54034ab64d9734f88bd.png)

**点击按钮后：**
![none-after](img/b31d04e7707033563b3166923084e457.png)

## 示例-2：使用 `hidden` 值

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>DOM Style borderTopStyle Property</title>
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
    <p>Click on the button to change the style of the border on the top</p>
    <div class="item">GeeksforGeeks</div>
    <button onclick="changeBorderTopStyle()">Change style</button>
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

**输出：**

**点击按钮前：**
![none-before](img/ee063f9103d1d54034ab64d9734f88bd.png)

**点击按钮后：**
![hidden-after](img/239d70012b3bd2fc0b3fc6f6daf1bc44.png)

## 示例-3：使用 `dotted` 值

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>DOM Style borderTopStyle Property</title>
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
    <p>Click on the button to change the style of the border on the top</p>
    <div class="item">GeeksforGeeks</div>
    <button onclick="changeBorderTopStyle()">Change style</button>
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

**输出：**

**点击按钮前：**
![none-before](img/ee063f9103d1d54034ab64d9734f88bd.png)

**点击按钮后：**
![dotted-after](img/1d499bb48dfa31b2c8ed7dfd8595c999.png)

## 示例-4：使用 `dashed` 值

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>DOM Style borderTopStyle Property</title>
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
    <p>Click on the button to change the style of the border on the top</p>
    <div class="item">GeeksforGeeks</div>
    <button onclick="changeBorderTopStyle()">Change style</button>
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

**输出：**

**点击按钮前：**
![none-before](img/ee063f9103d1d54034ab64d9734f88bd.png)

**点击按钮后：**
![dashed-after](img/bbb90520250d799a8a8d0fc4fb1eb77b.png)

## 示例-5：使用 `solid` 值

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>DOM Style borderTopStyle Property</title>
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
    <p>Click on the button to change the style of the border on the top</p>
    <div class="item">GeeksforGeeks</div>
    <button onclick="changeBorderTopStyle()">Change style</button>
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

**输出：**

**点击按钮前：**
![solid-before](img/1d830d30bab1514d8e04ad2b0cda7bbf.png)

**点击按钮后：**
![solid-after](img/f6c59f99c10442f1548db423b2061e79.png)

## 示例-6：使用 `double` 值

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>DOM Style borderTopStyle Property</title>
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
    <p>Click on the button to change the style of the border on the top</p>
    <div class="item">GeeksforGeeks</div>
    <button onclick="changeBorderTopStyle()">Change style</button>
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

**输出：**

**点击按钮前：**
![none-before](img/ee063f9103d1d54034ab64d9734f88bd.png)

**点击按钮后：**
![double-after](img/0a107a94b598e5edcc8040a822f8b783.png)

## 示例-7：使用 `groove` 值

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>DOM Style borderTopStyle Property</title>
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
    <p>Click on the button to change the style of the border on the top</p>
    <div class="item">GeeksforGeeks</div>
    <button onclick="changeBorderTopStyle()">Change style</button>
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

**输出：**

**点击按钮前：**
![none-before](img/ee063f9103d1d54034ab64d9734f88bd.png)

**点击按钮后：**
![groove-after](img/959d8467dd4c235073885f4815f8a21b.png)

## 示例-8：使用 `ridge` 值

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>DOM Style borderTopStyle Property</title>
    <style>
        .item {
            height: 50px;
            padding: 10px;
            border: 15px solid green;
        }
    </style>
</head>
```

# DOM Style borderTopStyle Property

## 示例-9: 使用插入值

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

### 输出:

**点击按钮前:**

![none-before](img/ee063f9103d1d54034ab64d9734f88bd.png)

**点击按钮后:**

![inset-after](img/7ec261007c51ae29de3127e5507439e3.png)

## 示例-10: 使用起始值

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

### 输出:

**点击按钮前:**

![outset-before](img/434000876950b9d5fb2840784dfbc16d.png)

**点击按钮后:**

![outset-after](img/f57df80812f9f131a1f185b8fbd00aee.png)

## 示例-11: 使用初始值

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

### 输出:

**点击按钮前:**

![none-before](img/ee063f9103d1d54034ab64d9734f88bd.png)

**点击按钮后:**

![initial-after](img/41dd52b81d6351dc1bc1019b8c4fac5d.png)

## 示例-12: 使用继承值

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

### 输出:

**点击按钮前:**

![inherit-before](img/fd1fa9fd2dd7c1226d9b6fa498e9897e.png)

**点击按钮后:**

![inherit-after](img/9237ba71af5591b6ee031245f7438e40.png)

## 支持的浏览器

由 `borderTopStyle` 属性支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   苹果 Safari