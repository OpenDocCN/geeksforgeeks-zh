# HTML |咏叹调-标签属性

> 原文:[https://www.geeksforgeeks.org/html-aria-label-attribute/](https://www.geeksforgeeks.org/html-aria-label-attribute/)

**咏叹调标签**有助于定义字符串，并为使用辅助技术的用户提供关于文档结构的附加信息。在大多数情况下，arial-label 用于用更精确的信息替换现有标签。然而，我们在使用 aria-label 时应该小心，因为它并不适用于所有的 HTML 元素。

aria-label 属性可以与 HTML 元素一起使用，例如:

*   挑选
*   文本区域
*   按钮
*   a(当 href="# "正在使用时)
*   音频和视频(当 control =“#”正在使用时)

aria-label 属性并不总是适用于像 span、p、div 这样的 HTML 元素。它可能适用于某些浏览辅助技术组合。

**语法:**

```html
<button aria-label="open" onclick="function()">CLICK</button>
```

这里会创建一个按钮，上面写着**【点击】**。aria-label–提供一个标签，通过使用辅助技术准确提及其输出/功能。

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
</head>

<body>
    <center>
        <h1 style="color:green">GeeksforGeeks</h1>
        <button value="open">open</button>

        <button aria-label="opens a new window" 
                value="open"> open </button>
    </center>
</body>

</html>
```

在这里，您可以看到一个 HTML 页面将会打开，并且包含并排的按钮，这些按钮彼此相同，没有任何区别。现在，如果有人正在使用 chrome 中的 chromevox 扩展功能，并在按 tab 键时打开耳机，那么当选择第一个按钮时，他们会听到单词**“打开”**，而当选择第二个按钮时，他们会听到短语**“打开新窗口”**。这在视力不好的人能看到两个按钮但不能理解上面写的文字的情况下特别有用。

**输出:**
**点击按钮前:**
![](img/3608125f2212f2deb204c19ac85d6e92.png)

**之后:**

<video class="wp-video-shortcode" id="video-347205-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://contribute.geeksforgeeks.org/wp-content/uploads/20190926_171451_Trim1.mp4?_=1">[https://contribute.geeksforgeeks.org/wp-content/uploads/20190926_171451_Trim1.mp4](https://contribute.geeksforgeeks.org/wp-content/uploads/20190926_171451_Trim1.mp4)</video>