# 如何使用 jQuery 在特定的 div 元素中应用 CSS？

> 原文:[https://www . geesforgeks . org/how-apply-CSS-in-special-div-element-use-jquery/](https://www.geeksforgeeks.org/how-to-apply-css-in-a-particular-div-element-using-jquery/)

在本文中，我们将使用 jQuery 设置 div 元素的 CSS。我们将使用 CSS 属性来设置 CSS。

**方法:**我们将创建一个包含一些文本和超链接的 div 元素。然后我们将使用 jQuery 对 div 元素应用 CSS。jQuery 自带函数。css()在这里我们可以获取和设置任何元素的 CSS。我们将把它用于 div 元素。

**语法:**

```html
<script>
    $("div").css("css-property","value");
</script>
```

### 示例 1:使用简单的 CSS

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8" />
    <meta name="viewport" 
        content="width=device-width" />

    <!-- Include jQuery file using CDN link-->
    <script src=
"https://code.jquery.com/jquery-3.6.0.min.js">
    </script>
</head>

<body>
    <!-- Our Body Content-->
    <div id="links">
        <h1>Welcome to GeeksforGeeks</h1>
        <a href=
"https://www.geeksforgeeks.org/data-structures">
            Data structures
        </a>
        <a href=
"https://www.geeksforgeeks.org/fundamentals-of-algorithms">
            Algorithms
        </a>
    </div>

    <!-- Using script inline to apply CSS-->
    <script>

        // Changing text color to green
        // and aligning to center
        $("div").css("color", "green");
        $("div").css("text-align", "center");
    </script>
</body>

</html>
```

### 输出:

![](img/490e0e3d26a6fccceede843583e07f9d.png)

### 示例 2:在元素上使用悬停效果

我们将使用 jQuery 的悬停函数，它采用两个函数。语法是

```html
$(element).hover(
    function(){
        // CSS during hover
    },
    function(){
        // CSS when not hovering
    },
);
```

下面是示例代码。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8" />
    <meta name="viewport" 
        content="width=device-width" />

    <!-- Include jQuery file using CDN link-->
    <script src=
"https://code.jquery.com/jquery-3.6.0.min.js">
    </script>
</head>

<body>
    <!-- Our Body Content-->
    <div id="links">
        <h1>Welcome to GeeksforGeeks</h1>
        <a href=
"https://www.geeksforgeeks.org/data-structures">
            Data structures
        </a>
        <a href=
"https://www.geeksforgeeks.org/fundamentals-of-algorithms">
            Algorithms
        </a>
    </div>

    <!-- Using script inline to apply CSS-->
    <script>

        // Changing text color to green
        // and aligning to center
        $("div").css("color", "green");
        $("div").css("text-align", "center");

        // Using hover function
        $("h1").hover(

            // First function is for during hover
            function () {
                $(this).css("font-size", 32);
            },

            // Second function is for before
            // or after hover
            function () {
                $(this).css("font-size", 24);
                $(this).css("transition-duration", "1s");
            }
        );
    </script>
</body>

</html>
```

### 输出

![](img/b893617836ac90e4b7e6c9938dd3d748.png)