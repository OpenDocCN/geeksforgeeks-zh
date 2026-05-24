# 如何使用 jQuery Mobile 制作垂直选择控件组？

> 原文:[https://www . geeksforgeeks . org/如何制作-垂直-选择-控制组-使用-jquery-mobile/](https://www.geeksforgeeks.org/how-to-make-vertical-selects-controlgroup-using-jquery-mobile/)

jQuery mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。

**包含脚本:**您可以通过将这些标签添加到您的 *<头>* 标签中，将 jQuery 移动脚本添加到您的项目中。

> <link rel="”stylesheet”" href="”http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”">
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
        <h4>Vertical Selects using jQuery Mobile</h4>
    </center>

    <fieldset data-role="controlgroup" />
    <legend>GeeksforGeeks</legend>

    <select name="gfg1" id="gfg">
        <option value="#">One</option>
        <option value="#">Two</option>
        <option value="#">Three</option>
    </select>

    <select name="gfg2" id="gfg">
        <option value="#">One</option>
        <option value="#">Two</option>
        <option value="#">Three</option>
    </select>

    <select name="gfg3" id="gfg">
        <option value="#">One</option>
        <option value="#">Two</option>
        <option value="#">Three</option>
    </select>
</body>

</html>
```

**输出:**

![](img/bc41e7398181de3119007ae7aab67cf4.png)

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
        <h4>Vertical Selects using jQuery Mobile</h4>
    </center>

    <fieldset data-role="controlgroup" />
    <legend>GeeksforGeeks</legend>
    <select name="gfg1" id="gfg">
        <option value="#">Geeks1</option>
        <option value="#">Geeks2</option>
        <option value="#">Geeks3</option>
    </select>

    <select name="gfg2" id="gfg">
        <option value="#">Geeks1</option>
        <option value="#">Geeks2</option>
        <option value="#">Geeks3</option>
    </select>

    <select name="gfg3" id="gfg">
        <option value="#">Geeks1</option>
        <option value="#">Geeks2</option>
        <option value="#">Geeks3</option>
    </select>
</body>

</html>
```

**输出:**

![](img/ca5450459e70166ee3fa01af39d1eea4.png)