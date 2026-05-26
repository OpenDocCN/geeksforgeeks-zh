# Underscore.js `_.isArray()` 功能

> 原文: [https://www.geeksforgeeks.org/underscore-js-_-isarray-function/](https://www.geeksforgeeks.org/underscore-js-_-isarray-function/)

Underscore.js 是一个 JavaScript 库，它提供了很多有用的功能，比如映射、过滤、调用等，甚至不使用任何内置对象。

`_.isArray()` 函数用于查找传递的参数是否为数组。数组是一组变量、常数和特殊符号。如果对象是数组，将返回 `true`，否则将返回 `false`。数组可以有不同的名称，并且可以是任何大小，甚至是零。

## 语法

```
_.isArray(object)
```

## 参数

只需要一个参数，即需要检查的对象 `object`。

## 返回值

如果传递的参数是数组，则返回 `true`，否则返回 `false`。

### 1. 向 `_.isArray()` 函数传递一个包含3个数字的数组

`_.isArray()` 函数接收传递的元素并检查它是否是一个数组。由于传递的参数是一组3个数字 – `1, 2, 3`。因此，它是一个数组。所以，最终输出将是 `true`。

**示例:**

```html
<html>
<head>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/underscore.js/1.9.1/underscore-min.js"></script>
</head>
<body>
    <script type="text/javascript">
        console.log(_.isArray([1, 2, 3]));
    </script>
</body>
</html>
```

**输出:**
![](img/ac8b0c488ea2120ae4940620781cea87.png)

### 2. 向 `_.isArray()` 函数传递一个字符数组

传递给 `_.isArray()` 函数的参数将被检查是否是一个数组。由于参数只包含一个字符 `"a"`，但它在 `[]` 方括号内，所以它是一个数组。因此答案是 `true`。

**示例:**

```html
<html>
<head>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/underscore.js/1.9.1/underscore-min.js"></script>
</head>
<body>
    <script type="text/javascript">
        console.log(_.isArray(["a"]));
    </script>
</body>
</html>
```

**输出:**
![](img/ac8b0c488ea2120ae4940620781cea87.png)

### 3. 向 `_.isArray()` 函数传递一个空数组

`_.isArray()` 函数接收元素 `[]`，然后检查它是否是一个数组。由于 `[]` 方括号内没有元素，所以它是空的。但因为有 `[]` 方括号，所以它是一个数组。因为空数组也是数组，所以输出是 `true`。

**示例:**

```html
<html>
<head>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/underscore.js/1.9.1/underscore-min.js"></script>
</head>
<body>
    <script type="text/javascript">
        console.log(_.isArray([]));
    </script>
</body>
</html>
```

**输出:**
![](img/ac8b0c488ea2120ae4940620781cea87.png)

### 4. 向 `_.isArray()` 函数传递一个数字

如果我们向 `_.isArray()` 函数传递任意数字，它将检查参数是否是一个数组。由于传递给 `_.isArray()` 函数的是一个数字，因此输出将是 `false`。

**示例:**

```html
<html>
<head>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/underscore.js/1.9.1/underscore-min.js"></script>
</head>
<body>
    <script type="text/javascript">
        console.log(_.isArray(1));
    </script>
</body>
</html>
```

**输出:**
![](img/c9f4eb55364a488f60fb6c2ded5b9036.png)

**注意:**
这些命令在 Google 控制台或 Firefox 中无法工作，因为这些额外的文件需要添加，而它们没有添加。
因此，将给定的链接添加到您的 HTML 文件中，然后运行它们。链接如下:

```html
<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/underscore.js/1.9.1/underscore-min.js"></script>
```