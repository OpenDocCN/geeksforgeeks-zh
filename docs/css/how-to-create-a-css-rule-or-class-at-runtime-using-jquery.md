# 如何使用 jQuery 在运行时创建 CSS 规则或类？

> 原文:[https://www . geesforgeks . org/如何在运行时使用-jquery 创建-CSS-规则或类/](https://www.geeksforgeeks.org/how-to-create-a-css-rule-or-class-at-runtime-using-jquery/)

为我们的 **[HTML](https://www.geeksforgeeks.org/html-tutorials/)** 写一个 **[CSS](https://www.geeksforgeeks.org/css-tutorials/)** 文件是一个惯例。那些叫做静态 CSS。当我们想要在运行时创建级联样式表规则时，我们需要 **[jQuery](https://www.geeksforgeeks.org/jquery-tutorials/)** 。jQuery 使我们能够动态地将样式应用于我们的 HTML。

CSS 规则一旦被编写，就可以存储在一个变量中，并在任何需要的地方多次使用。
我们使用 jQuery 的**CSS(“arrtibute 1”，“value 1”)**。

下面的例子说明了这种方法:

**例 1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS Rules with JQuery</title>
    <script 
src="https://code.jquery.com/jquery-3.4.1.js" 
integrity="sha256-WpOohJOqMqqyKL9FccASB9O0KwACQJpFTUBLTYOVvVU=" 
crossorigin="anonymous">
    </script>
</head>

<body>
    <div id="myId">
        <h1>GeeksforGeeks</h1>
    </div>

    <div class="myclass">
        <h1>A Computer Science Portal for Geeks</h1>
    </div>

    <script>

        // Here 'my_css' variable stores the Style
        var my_css = {
            backgroundColor: "red",
            color: "rgb(0,255,0)"
        }
        $("#myId").css(my_css);

        var my_class_css = {
            background: "green",
            color: "rgb(255,255,255)"
        }
        $(".myclass").css(my_class_css);
    </script>

</body>

</html>
```

**输出:**
![](img/cd2f8de223426afde7b66c8e3b08fdf9.png)

**示例 2:** 它还有一个替代方案，可以直接使用类似 CSS 的样式代码，而不是类似 JavaScript 的样式。

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS Rules with JQuery</title>
    <script 
src="https://code.jquery.com/jquery-3.4.1.js" 
integrity="sha256-WpOohJOqMqqyKL9FccASB9O0KwACQJpFTUBLTYOVvVU=" 
crossorigin="anonymous">
  </script>
</head>

<body>
    <div id="myId">
        <h1>Without Coding</h1>
    </div>

    <div class="myclass">
        <h1>There are no Geeks</h1>
    </div>

    <script>
        $(document).ready(function() {

            // Build your CSS.
            var body_css = {
                "background-color": "rgb(0,0,0)",
                "font-weight": "",
                "color": "rgb(255,255,255)"
            }

            $("body").css(body_css);
        });
    </script>

</body>

</html>
```

**输出:**
![](img/7a095e1f46dfc0a5ea2463246c85522c.png)