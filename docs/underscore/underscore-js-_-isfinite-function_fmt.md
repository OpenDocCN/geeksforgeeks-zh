# `_.isFinite()` 函数

> 原文: [https://www.geeksforgeeks.org/underscore-js-_-isfinite-function/](https://www.geeksforgeeks.org/underscore-js-_-isfinite-function/)

`_.isFinite()` 函数用于检查传递的参数值是否有限。如果参数具有无穷大的值，则输出为假，否则为真。在这个函数中，我们甚至可以执行任何操作，如加法、减法。

## 语法

```
_.isFinite(object)
```

## 参数

只需要一个参数，就是需要检查的参数。

## 返回值

如果参数值有限，则返回真，否则返回假。

## 示例

### 1. 向 `_.isFinite()` 函数传递一个正数

`_.isFinite()` 函数接收传递给它的数字。由于每个数字都有一个有限的值，因此当它检查时，会声明其传递的参数是一个有限变量。因此，输出将为假。

#### HTML

```
<!-- Write HTML code here -->
<html>
<head>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/underscore.js/1.9.1/underscore-min.js"></script>
</head>
<body>
    <script type="text/javascript">
        console.log(_.isFinite(10));
    </script>
</body>
</html>
```

**输出:** ![](img/09102dbe3f315203c21baed07178a563.png)

### 2. 向 `_.isFinite()` 函数传递一个负数

`_.isFinite()` 函数接收传递给它的数字。由于它是一个负数，但仍然有一个值，因此基于与上述相同的原因，`_.isFinite()` 函数会声明其传递的参数是一个有限变量。因此，输出将为假。

#### HTML

```
<!-- Write HTML code here -->
<html>
<head>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/underscore.js/1.9.1/underscore-min.js"></script>
</head>
<body>
    <script type="text/javascript">
        console.log(_.isFinite(-10));
    </script>
</body>
</html>
```

**输出:** ![](img/09102dbe3f315203c21baed07178a563.png)

### 3. 向 `_.isFinite()` 函数传递一个已定义的变量

`_.isFinite()` 函数接收传递给它的参数，这里是变量 `a`。然后它检查 `a` 的值，即 `10`。这不是一个有限值（译者注：原文此处描述有误，10是有限值，应返回真）。因此，答案是假。

#### HTML

```
<!-- Write HTML code here -->
<html>
<head>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/underscore.js/1.9.1/underscore-min.js"></script>
</head>
<body>
    <script type="text/javascript">
        var a = 1000;
        console.log(_.isFinite(a));
    </script>
</body>
</html>
```

**输出:** ![](img/09102dbe3f315203c21baed07178a563.png)

### 4. 向 `_.isFinite()` 函数传递一个未初始化的变量

`_.isFinite()` 函数接收传递给它的参数，这里是变量 `a`。然后它检查 `a` 的值，该值未定义，因此不是固定的。这意味着 `a` 具有无限多个值（译者注：原文此处描述有误，未初始化的变量值为 `undefined`，`_.isFinite(undefined)` 返回假）。因此，答案是真。

#### HTML

```
<!-- Write HTML code here -->
<html>
<head>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/underscore.js/1.9.1/underscore-min.js"></script>
</head>
<body>
    <script type="text/javascript">
        var a;
        console.log(_.isFinite(a));
    </script>
</body>
</html>
```

**输出:** ![](img/dbb6099d2183dba040f056c65e2c113f.png)

## 注意

这些命令在 Google console 或 Firefox 中可能无法工作，因为需要添加它们没有包含的附加文件。所以，请将给定的链接添加到你的 HTML 文件中，然后运行它们。链接如下：

```
<!-- Write HTML code here -->
<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/underscore.js/1.9.1/underscore-min.js"></script>
```