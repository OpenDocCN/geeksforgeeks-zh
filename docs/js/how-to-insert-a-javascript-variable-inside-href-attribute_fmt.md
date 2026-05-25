# 如何在 href 属性内部插入一个 JavaScript 变量？

> 原文: [https://www.geeksforgeeks.org/how-to-insert-a-javascript-variable-inside-href-attribute/](https://www.geeksforgeeks.org/how-to-insert-a-javascript-variable-inside-href-attribute/)

`<a>…</a>`标签用于在 HTML 中创建超链接。
标签的属性之一是`href`。

**`href`**: 指定链接指向的页面的 URL。

## 示例:

```html
<a href="https://www.geeksforgeeks.org/">
    GeeksforGeeks
</a>
```

## 在`href`属性中使用变量的方法:

### 1. 使用 onclick 属性

此方法使用`a`标签的`onclick`属性。即，每当链接（`a`标签）被点击时，会触发一个`onclick`事件。我们将使用此`onclick`事件来生成一个新的 URL 并将用户重定向到该 URL。（注意：此 URL 将包含我们想要在`href`属性中使用的变量）

**步骤:**
首先，我们需要了解以下术语：

*   `location.href` -> 是当前页面的整个 URL。
*   `this` -> 指的是已经被点击的`a`标签。
*   `this.href` -> 从`a`标签中获取`href`值。

一旦我们有了`this.href`，就将变量附加到它上面（这里我们使用了一个名为`XYZ`的变量）。
然后我们需要将值附加到 URL。
现在我们的网址已经准备好了变量及其附加值。

在下面的例子中，我们将添加一个名为`XYZ`的变量，其值为 55。

```html
<!DOCTYPE html>
<html>
<head>
    <title>GeeksforGeeks</title>
    <script>
        var val = 55;
    </script>
</head>
<body>
    Link to <a href="https://www.google.com/"
        onclick="location.href=this.href+'?xyz='+val;return false;">
        Google
    </a>
</body>
</html>
```

```
Resultant Url: https://www.google.com/?xyz=55
```

`val`是一个 JavaScript 变量，它存储了我们想要传递给 URL 的值。
URL 有一个名为`XYZ`的变量，该变量从 JavaScript 变量`val`中取值= 55。

### 2. 使用 document.write

`document`: 当一个 HTML 文档被加载到 Web 浏览器中时，它就变成了一个文档对象。
这个文档对象有几个函数，其中之一是`write()`。
`write()`: 将 HTML 表达式或 JavaScript 代码写入文档。
在此方法中，我们将使用此`write()`函数来创建一个`a`标签。

```html
<!DOCTYPE html>
<html>
<head>
    <title>GeeksforGeeks</title>
    <script>
        var val = 55;
    </script>
</head>
<body>
    Link to
    <script>
        var loc = "https://www.google.com/?xyz="+val;
        document.write('<a href="' + loc + '">Google</a>');
    </script>
</body>
</html>
```

```
Resultant Url: https://www.google.com/?xyz=55
```

`val`是一个 JavaScript 变量，它存储了我们想要传递给 URL 的值。
URL 有一个名为`XYZ`的变量，该变量从 JavaScript 变量`val`中取值= 55。