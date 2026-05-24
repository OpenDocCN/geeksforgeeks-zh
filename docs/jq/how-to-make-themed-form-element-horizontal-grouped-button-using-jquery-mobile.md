# 如何使用 jQuery Mobile 制作主题表单元素水平分组按钮？

> 原文:[https://www . geesforgeks . org/how-to-make-theme-form-element-horizontal-group-button-use-jquery-mobile/](https://www.geeksforgeeks.org/how-to-make-themed-form-element-horizontal-grouped-button-using-jquery-mobile/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile 制作主题表单元素水平分组按钮。

**方法:**首先，添加项目所需的 jQuery Mobile 脚本。

> <link rel="”stylesheet”" href="”http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”/">
> <脚本 src = " http://code . jquery . com/jquery-1 . 11 . 1 . min . js "></脚本>
> <脚本 src = " http://code . jquery . com/mobile/1 . 4 . 5/jquery . mobile-1 . 4 . 5 . min . js "></脚本>

**例 1:**

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
            Themed Form element Horizontal 
            grouped button using jQuery Mobile
        </h4>
    </center>

    <div data-role="controlgroup" 
        data-type="horizontal" data-theme="b">

        <button id="gfg" data-role="button" 
            data-icon="plus">plus
        </button>

        <button id="gfg" data-role="button" 
            data-icon="minus">minus
        </button>

        <button id="gfg" data-role="button" 
            data-icon="star">star
        </button>
    </div>
</body>

</html>
```

**输出:**

![](img/8cfd1cc7eec33a25110108043ca87ca1.png)

**例 2:**

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
            Themed Form element Horizontal 
            grouped button using jQuery Mobile
        </h4>
    </center>

    <div data-role="controlgroup" 
        data-type="horizontal" data-theme="b">

        <a href="https://www.geeksforgeeks.org/"
            data-role="button" data-icon="plus">
            plus
        </a>

        <a href="https://www.geeksforgeeks.org/"
            data-role="button" data-icon="minus">
            minus
        </a>

        <a href="https://www.geeksforgeeks.org/"
            data-role="button" data-icon="star">
            star
        </a>
    </div>
</body>

</html>
```

**输出:**

![](img/8cfd1cc7eec33a25110108043ca87ca1.png)