# 如何使用 jQuery Mobile 制作阴影按钮？

> 原文:[https://www . geesforgeks . org/how-to-make-a-shadow-button-use-jquery-mobile/](https://www.geeksforgeeks.org/how-to-make-a-shadow-button-using-jquery-mobile/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile 制作一个阴影按钮。

**方法:**首先，添加项目所需的 jQuery Mobile 脚本。

> <link rel="”stylesheet”" href="”http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”">
> <脚本 src = " http://code . jquery . com/jquery-1 . 11 . 1 . min . js "></脚本>
> <脚本 src = " http://code . jquery . com/mobile/1 . 4 . 5/jquery . mobile-1 . 4 . 5 . min . js "></脚本>

我们将使用不同类型的 ui 类和类型来组成标记按钮。

**示例 1:** 在这个示例中，我们将使用带有“ui-btn ui-shadow”类的锚点标记来制作按钮。

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
            Shadowed Anchor using 
            jQuery Mobile
        </h4>
    </center>

    <a href="#" class="ui-btn ui-shadow">
        Shadowed Anchor
    </a>
</body>

</html>
```

**输出:**

![](img/a1d63d175ee3e3feea56af2e01cd45f2.png)

**示例 2:** 在本例中，我们将使用带有 class =“ui-BTN ui-shadow”的 button 标记来创建带有 shadow 的 button。

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

        <h4>Shadowed Button using jQuery</h4>
    </center>

    <button class="ui-btn ui-shadow">
        Shadowed Button
    </button>
</body>

</html>
```

**输出:**

![](img/f8fe6bfa0e21396a36ebeaa8d79034a1.png)