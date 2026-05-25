# 如何在 Javascript 中将特殊字符转换成 HTML？

> 原文：[https://www.geeksforgeeks.org/how-to-convert-special-characters-to-html-in-javascript/](https://www.geeksforgeeks.org/how-to-convert-special-characters-to-html-in-javascript/)

在 HTML 中，有许多情况下，浏览器在呈现页面时会感到困惑。在 HTML 中，小于号（`<`）意味着某个标签的开始，如果我们把一个元素放在它后面，比如`'a'`或`'h'`，那么浏览器会将它们分别识别为锚点标签和标题标签。类似的情况还有一些特殊字符，包括小于、`@`、`&`和`\`等。

## 问题示例

此示例说明了 HTML 文本未转换为特殊格式时导致的问题。

```html
<html>
    <head>
    </head>
    <body>
        <div>
        If b<a and a<h then b<h. 
<!-- the browser understands it as anchor tag--> 
       </div>
    </body>
</html>
```

`b < a`这部分有问题。浏览器将其理解为锚点标签。类似的情况还有`b < h`。

**输出：**

```
If b
```

## 解决方法 1

一种解决方法是手动将特殊符号替换为有问题的相应特殊字符的 HTML 实体。但是对于非常大的网站来说，很难找出所有的字符，然后用 HTML 呈现出来。

```html
<html>
<head>
</head>
<body>
    <div>
        If b
        &lt; a and ab &lt; h then b &lt; h. 
      <!-- the browser understands it as less than-->
    </div>
</body>
</html>
```

**输出：**

```
If b < a and ab < h then b < h.
```

## 基于 javascript 的解决方案

另一种方法是使用 JavaScript 将每个特殊字符转换为各自的 HTML 实体。在脚本中，我们将借助一个正则表达式来替换所有的特殊字符为`"&#" + 字符的 ASCII 值 + ";"`。我们对页面上的所有文本应用相同的规则。

```html
<html>
<head>
    <script>
        function Encode(string) {
            var i = string.length,
                a = [];

            while (i--) {
                var iC = string[i].charCodeAt();
                if (iC < 65 || iC > 127 || (iC > 90 && iC < 97)) {
                    a[i] = '&#' + iC + ';';
                } else {
                    a[i] = string[i];
                }
            }
            return a.join('');
        }
    </script>
</head>
<body>
    <script>
        document.write(Encode("If b<a and a<h then b<h"));
    </script>
</body>
</html>
```

**输出：**

```
If b&lt;a and a&lt;h then b&lt;h
```