# 如何使用 jQuery Mobile 制作迷你大小的分组按钮页脚？

> 原文:[https://www . geesforgeks . org/how-mini-size-group-button-footer-use-jquery-mobile/](https://www.geeksforgeeks.org/how-to-make-mini-sized-grouped-button-footer-using-jquery-mobile/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile 制作迷你大小的分组按钮页脚。

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
            Mini grouped button footer 
            in jQuery Mobile
        </h4>
    </center>

    <div data-role="controlgroup" 
        data-type="horizontal" data-mini="true"
        data-role="footer" class="ui-bar">

        <a href="https://www.geeksforgeeks.org/"
            data-icon="plus">A</a>

        <a href="https://www.geeksforgeeks.org/"
            data-icon="minus">B</a>

        <a href="https://www.geeksforgeeks.org/"
            data-icon="arrow-u">C</a>

        <a href="https://www.geeksforgeeks.org/"
            data-icon="arrow-d">D</a>

        <a href="https://www.geeksforgeeks.org/"
            data-icon="arrow-l">E</a>

        <a href="https://www.geeksforgeeks.org/"
            data-icon="arrow-r">F</a>
    </div>
</body>

</html>
```

**输出:**

![](img/d7c9f731dd3c7f677ab0143ad38863d0.png)

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
            Mini grouped button footer
            in jQuery Mobile
        </h4>
    </center>

    <div data-role="controlgroup" data-type="horizontal" 
        data-mini="true" data-role="footer" class="ui-bar">
        <button id="gfg" data-icon="plus">A</button>
        <button id="gfg" data-icon="minus">B</button>
        <button id="gfg" data-icon="arrow-u">C</button>
        <button id="gfg" data-icon="arrow-d">D</button>
        <button id="gfg" data-icon="arrow-l">E</button>
        <button id="gfg" data-icon="arrow-r">F</button>
    </div>
</body>

</html>
```

**输出:**

![](img/d7c9f731dd3c7f677ab0143ad38863d0.png)