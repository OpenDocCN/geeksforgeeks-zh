# jQuery | :lang()选择器

> 原文:[https://www.geeksforgeeks.org/jquery-lang-selector/](https://www.geeksforgeeks.org/jquery-lang-selector/)

**:郎选择器**用于选择所有具有指定值的**郎属性**的元素。
该属性包含*单值语言 _ 代码*，用于指定内容的语言。一些语言的例子是英语的**“en”**，西班牙语的**“es”**等等。它将整个单词作为值，如 **lang=" en"** 或后跟连字符(-)如 **lang=" en-us"** 。

**语法:**

```html
$(":lang(language)")
```

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
    <script>
        $(document).ready(function() {
            $("p:lang(en)").css(
                "background-color", "coral");
        });
    </script>
</head>

<body>
    <center>
        <h1 style="color:green;">
          GeeksForGeeks</h1>
        <h2>jQuery :lang Selector
      </h2>
        <p>GeeksforGeeks</p>
        <p lang="en">
            A computer science portal for geeks.</p>
    </center>

</body>

</html>
```

**输出:**
![](img/830226d6202e7203b25513a85a72952b.png)

**支持的浏览器:**以下是 **jQuery :lang Selector** 支持的浏览器:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队