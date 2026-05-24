# script.aculo.us InPlaceEditor

> 原文: [https://www.geeksforgeeks.org/script-aculo-us-inplaceeditor/](https://www.geeksforgeeks.org/script-aculo-us-inplaceeditor/)

`script.aculo.us`库是一个跨浏览器库，旨在改善网站的用户界面。`Ajax.InPlaceEditor`用于使元素可编辑，从而允许用户编辑页面上的内容并将更改提交给服务器。

`InPlaceEditor`类用于定义一个可编辑字段，该字段可以请求文件访问其内容。我们可以指定需要转换成就地编辑器的元素、请求的URL以及传递不同参数的选项。

**语法:**

```
Ajax.InPlaceEditor(element, url, options);
```

**值:**

*   `element`: 这是我们想要添加可编辑文本字段的元素。
*   `url`: 向其发出AJAX请求的url或文件路径。
*   `options`: 自定义编辑器的附加字段。

**示例:**

要演示这个函数的用法，请遵循下面的代码。实现了一个JavaScript代码，它为特定的元素创建了一个就地编辑器。代码所需的网址是`test.html`，其中有一个简单的文本`GeeksforGeeks`。点击`Click me`，你会看到原位编辑器。
点击`OK`，将获取`test.html`页面内容的内容。

## HTML

```
<!DOCTYPE html>
<html>

<head>
    <!-- Include the required scripts -->
    <script type="text/javascript"
        src="prototype.js"> 
    </script>

<script type="text/javascript"
        src="scriptaculous.js?load=effects,controls"> 
    </script> 
</head>

<body>
    <p id="editme">Click me</p>
    <!-- JavaScript part to initialize the objects -->
    <script type="text/javascript">
        new Ajax.InPlaceEditor('editme', 'test.html');
    </script>
</body>

</html>
```

**输出:**

![](img/b61a0ec4de845c698b1bad5e3359c44e.png)

`test.html`是文件`test.html`的代码，该文件在上面的示例代码中用作URL。

```
<!DOCTYPE html> 
<html>

<body> 
    GeeksforGeeks
</body>

</html> 
```