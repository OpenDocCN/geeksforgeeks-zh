# 如何使用 jQuery 在父代的最后一个子代中应用 CSS？

> 原文:[https://www . geesforgeks . org/how-apply-CSS-in-last-child-of-parent-use-jquery/](https://www.geeksforgeeks.org/how-to-apply-css-in-last-child-of-parent-using-jquery/)

在本文中，我们将看到如何使用 jQuery 在父元素的最后一个子元素中设置样式。要在父级的最后一个子级上设置样式，我们使用 [jQuery:最后一个子级选择器](https://www.geeksforgeeks.org/jquery-last-child-selector/)。

**:最后一个子元素选择器**用于选择其父元素的最后一个子元素。

**语法:**

```html
$("Selector:last-child")
```

**方法:**首先，我们创建一个包含 div 元素的 HTML 元素。这个 div 元素包含一些段落元素，然后我们使用:最后一个子选择器来选择父元素的最后一个段落。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>

    <style>
        div {
            font-size: 18px;
            font-weight: bold;
        }

        p {
            margin-left: 50px;
        }
    </style>

    <script>
        $(document).ready(function() {
            $("p:last-child").css({
                backgroundColor: "green",
                color: "white",
                padding: "5px 15px",
                display: "table"
            });
        });
    </script>
</head>

<body>
    <h1 style="color: green;">GeeksforGeeks</h1>

    <h3>
        How to apply CSS in last child of 
        parent using jQuery library?
    </h3>

    <div>
        <span>GeeksforGeeks Courses:</span>
        <p>Data Structure</p>
        <p>C++ Programming</p>
        <p>javaScript</p>
        <p>Web Technology</p>
    </div>
</body>

</html>
```

**输出:**

![](img/57051aa4749de1248483dadef7edf7c5.png)