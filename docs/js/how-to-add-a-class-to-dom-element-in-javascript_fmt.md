# 如何在 JavaScript 中给 DOM 元素添加一个类？

> 原文：[https://www.geeksforgeeks.org/how-to-add-a-class-to-dom-element-in-javascript/](https://www.geeksforgeeks.org/how-to-add-a-class-to-dom-element-in-javascript/)

`DOM`（文档对象模型）是一种操作文档（HTML 文档）的方式。本文将讨论如何访问和设置 DOM 元素的类名。在 DOM 中，所有的 HTML 元素都被定义为对象。我们将使用针对 CSS 的 Javascript 来操纵它们。

下面是 Javascript 的属性，我们将使用这些属性向 DOM 元素添加一个类：

## 使用 `classList` 属性

`classList` 属性将类名作为一个 `DOMTokenList` 对象返回。它有一个叫 `add` 的方法，用来给元素添加类名。

### 语法

```javascript
element.classList.add("className")
```

### 示例

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        .geek {
            background-color: green;
            font-size: 50px;
        }
    </style>
</head>

<body>

<button onclick="myClass()">Try it</button>

<div id="gfg">Geeks for Geeks</div>

<script>
        function myClass() {
            var elem = document.getElementById("gfg");

            // Adding class to div element
            elem.classList.add("geek");
        }
    </script>

</body>

</html>
```

### 输出

**点击按钮前：**

![](img/1d05618490a6430ff8746aad76cbe190.png)

**点击按钮后：**

![](img/366368e75060bd83b0a84b3ad45cba25.png)

## 使用 `className` 属性

`className` 属性返回元素的类名。如果元素已经有一个类，那么它将简单地添加另一个类，否则它将向它追加我们的新类。

### 语法

```javascript
HTMLElementObject.className
```

### 示例

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        .geekClass {
            background-color: green;
            text-align: center;
            font-size: 50px;
        }
    </style>
</head>

<body>

<div id="gfg">
        Geeks For Geeks
    </div>

<button onclick="myClassName()">Add Class</button>

<script>
        function myClassName() {
            var element = document.getElementById("gfg");

            // Adding the class geekClass to element
            // with id gfg space is given in className
            // (" geekClass") as if there is already
            // a class attached to an element than our
            // new class won't overwrite and will append
            // one more class to the element
            element.className += " geekClass";
        }
    </script>

</body>

</html>
```

### 输出

**点击按钮前：**

![](img/f0a047a1fc1e1a37873cfdee3efb3618.png)

**点击按钮后：**

![](img/c39387a68f08ab37672b6aba24f278bb.png)

## 支持的浏览器

`classList` 属性支持的浏览器如下：

*   Chrome 8+
*   Opera 11.5+
*   Safari 5.1+
*   Edge 10+
*   Mozilla Firefox 3.6+