# 如何使用 jQuery Mobile 制作内嵌按钮？

> 原文:[https://www . geeksforgeeks . org/如何使用-jquery-mobile/](https://www.geeksforgeeks.org/how-to-make-a-inline-button-using-jquery-mobile/) 制作内联按钮

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile 制作一个内嵌按钮。

**方法:**首先，添加项目所需的 jQuery Mobile 脚本。

> <link rel="”stylesheet”" href="”http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”">
> <脚本 src = " http://code . jquery . com/jquery-1 . 11 . 1 . min . js "></脚本>
> <脚本 src = " http://code . jquery . com/mobile/1 . 4 . 5/jquery . mobile-1 . 4 . 5 . min . js "></脚本>

我们将使用不同类型的用户界面类和类型来组成标记按钮。

**示例 1:** 我们将使用带有 class =“ui-BTN ui-BTN-inline”的 Button 来制作按钮。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <link rel="stylesheet" href=
"http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css" />

    <script src=
        "http://code.jquery.com/jquery-1.11.1.min.js">
    </script>

    <script src=
"http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js">
    </script>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>
        <h4>Inlined Button using jQuery Mobile</h4>
    </center>

    <button class="ui-btn ui-btn-inline">
        Inlined Button
    </button>
</body>

</html>
```

**输出:**

![](img/ebe54d755aec25c7cc7f61930dda190e.png)

**示例 2:** 我们将使用带有 class =“ui-BTN ui-BTN-inline”的 Anchor 标记来实现我们的目的。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <link rel="stylesheet" href=
"http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css" />

    <script src=
        "http://code.jquery.com/jquery-1.11.1.min.js">
    </script>

    <script src=
"http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js">
    </script>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>
        <h4>
            Inlined Anchor using 
            jQuery Mobile
        </h4>
    </center>

    <a href="#" class="ui-btn ui-btn-inline">
        Inlined Anchor
    </a>
</body>

</html>
```

**输出:**

![](img/79f7c8b38eb68ac316b9386bce05532a.png)