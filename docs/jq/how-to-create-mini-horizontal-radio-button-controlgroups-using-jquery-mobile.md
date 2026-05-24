# 如何使用 jQuery Mobile 创建迷你水平单选按钮控件组？

> 原文:[https://www . geesforgeks . org/如何创建-迷你-水平-单选按钮-控制组-使用-jquery-mobile/](https://www.geeksforgeeks.org/how-to-create-mini-horizontal-radio-button-controlgroups-using-jquery-mobile/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile 制作一个迷你水平单选按钮控件组按钮。

**方法:**首先，添加项目所需的 jQuery Mobile 脚本。

> <link rel="”stylesheet”" href="”http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”">
> <脚本 src = " http://code . jquery . com/jquery-1 . 11 . 1 . min . js "></脚本>
> <脚本 src = " http://code . jquery . com/mobile/1 . 4 . 5/jquery . mobile-1 . 4 . 5 . min . js "></脚本>

**例 1:**

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
            Mini Horizontal Radio button
            using jQuery Mobile
        </h4>
    </center>

    <fieldset data-role="controlgroup" 
        data-type="horizontal" data-mini="true">
        <legend>GeeksforGeeks</legend>

        <input type="radio" name="gfg" 
            id="gfg1" value="on" />
        <label for="gfg1">first</label>

        <input type="radio" name="gfg" id="gfg2" 
            value="off" checked="checked" />
        <label for="gfg2">second</label>

        <input type="radio" name="gfg" 
            id="gfg3" value="other" />
        <label for="gfg3">Third</label>
    </fieldset>
</body>

</html>
```

**输出:**

![](img/1d530ebd3fb378a7606cc97cc9819e93.png)

**例 2:**

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
            Mini Horizontal Radio button
            using jQuery Mobile
        </h4>
    </center>

    <fieldset data-role="controlgroup" 
        data-type="horizontal" data-mini="true">
        <legend>GeeksforGeeks</legend>
        <input type="radio" name="gfg" id="gfg1"
            value="on" checked="checked" />
        <label for="gfg1">Geeks1</label>
        <input type="radio" name="gfg" 
            id="gfg2" value="off" />
        <label for="gfg2">Geeks2</label>
        <input type="radio" name="gfg" 
            id="gfg3" value="other" />
        <label for="gfg3">Geeks3</label>
    </fieldset>
</body>

</html>
```

**输出:**

![](img/33f0ca5603df9c64d47b3325cfeee28b.png)