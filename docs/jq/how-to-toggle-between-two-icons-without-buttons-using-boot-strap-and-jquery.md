# 如何使用 boot-strap 和 jQuery 在两个没有按钮的图标之间切换？

> 原文:[https://www . geesforgeks . org/如何在不带按钮的两个图标之间切换-使用引导带和-jquery/](https://www.geeksforgeeks.org/how-to-toggle-between-two-icons-without-buttons-using-boot-strap-and-jquery/)

给定一个带有两个图标的 HTML 文档，任务是在用户每次单击图标时交替显示图标。这个任务可以在 jQuery(一个 JavaScript 库)的帮助下轻松完成。

**方法:**方法是简单地给两个图标添加一个“点击”事件监听器，并使用 jQuery 切换两个图标的 CSS 类。这些类最终负责显示图标库中的特定图标(在本例中为 Fontawesome)。这里，我们使用了两个图标，

1.  一个是“菜单栏”(菜单图标)类名
2.  一个带有“fa-times”类名(十字图标)

每当用户点击菜单图标时，它的“fa-bar”类就会切换到“fa-times”，这样十字图标就会显示出来，反之亦然。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content=
        "width=device-width,initial-scale=1.0" />

    <!--Bootstrap CSS CDN-->
    <link rel="stylesheet" href=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css"
        integrity=
"sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm"
        crossorigin="anonymous" />

    <!--Font Awesome Icons-->
    <script src="https://kit.fontawesome.com/f2c150d561.js"
        crossorigin="anonymous">
    </script>

    <!--jQuery CDN-->
    <script src="https://code.jquery.com/jquery-3.2.1.slim.min.js"
        integrity=
"sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN"
        crossorigin="anonymous">
    </script>
</head>

<body>
    <!--First Icon-->
    <i class="fas fa-bars m-5" style="font-size: 60px;"></i>

    <script>
        $(".fas").click(function () {
            $(".fas").toggleClass("fa-bars fa-times");
        });
    </script>
</body>

</html>
```

**输出:**

![](img/55774b2389d4df0fddbbe2335326d23a.png)