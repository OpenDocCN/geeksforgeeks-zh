# jQuery |:根选择器

> 原文:[https://www.geeksforgeeks.org/jquery-root-selector/](https://www.geeksforgeeks.org/jquery-root-selector/)

jQuery 中的**:根选择器**用于选择文档的根元素。

**语法:**

```html
$(":root")
```

**参数:**该选择器包含单参数*根*，是文档的根元素。

**示例:**本示例使用:根选择器选择文档，并将背景颜色设置为绿色。

```html
<!DOCTYPE html>
<html>

<head> 
    <title>
        jQuery :root Selector
    </title>

    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
</head> 

<body style = "text-align:center;">

    <h1>GeeksForGeeks</h1>

    <h2>jQuery :root Selector</h2>

    <!-- Script uses :root selector -->
    <script>
        $(document).ready(function() {
            $(":root").css("background-color", "green");
        });
    </script>
</body>

</html>
```

**输出:**
![](img/2256e72a4d2ec2b3b1575262a726f480.png)