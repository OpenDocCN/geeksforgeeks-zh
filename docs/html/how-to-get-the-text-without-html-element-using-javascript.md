# 如何用 JavaScript 获取没有 HTML 元素的文本？

> 原文:[https://www . geesforgeks . org/如何使用 javascript 获取不带 html 元素的文本/](https://www.geeksforgeeks.org/how-to-get-the-text-without-html-element-using-javascript/)

给定一个包含一些元素的 HTML 文档，任务是使用 JavaScript 获取 HTML 元素中的文本。有两种方法可以获取没有 HTML 元素的文本，如下所示:

1.  使用[内部文本属性](https://www.geeksforgeeks.org/html-dom-innerhtml-property/)
2.  使用[文本内容属性](https://www.geeksforgeeks.org/html-dom-textcontent-property/)

**使用 innerText 属性:**我们可以使用 innerText 属性从 HTML 元素中获取文本。

**示例:**

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        Get the text inside HTML
        element using JavaScript
    </title> 
</head>

<body>
    <div class="main">
        Welcome to GeeksforGeeks
    </div>

    <script>
        const div = document.querySelector('.main');

        alert(div.innerText);
    </script>
</body>

</html>
```

**输出:**
![](img/3b5c6323db19c696868904f7dabf20b3.png)

**使用 textContent 属性:**我们还可以使用 textContent 属性从 HTML 元素中获取文本。

**示例:**

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        Get the text inside HTML
        element using JavaScript
    </title> 
</head>

<body>
    <div class="main">
        Welcome to GeeksforGeeks
    </div>

    <script>
        const div = document.querySelector('.main');

        alert(div.textContent);
    </script>
</body>

</html>
```

**输出:**
![](img/3b5c6323db19c696868904f7dabf20b3.png)

**内部文本和文本内容的区别:**

1.  `innerText`属性只返回**人类可读的**文本，而`textContent`属性返回包括`<script>`和`<style>`标签在内的所有文本。
2.  `innerText`属性处理元素的样式，不返回任何隐藏的元素，而`textContent`属性返回包括隐藏元素在内的所有元素。
3.  `innerText`属性仅针对**元素**对象定义，而`textContent`属性针对所有**节点**对象定义。