# 如何使用 jQuery Mobile 创建迷你按钮？

> 原文:[https://www . geeksforgeeks . org/如何使用-jquery-mobile/](https://www.geeksforgeeks.org/how-to-create-a-mini-button-using-jquery-mobile/) 创建迷你按钮

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile 制作一个迷你按钮。

**方法:**首先，添加项目所需的 jQuery Mobile 脚本。

> <link rel="”stylesheet”" href="”http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”">
> <脚本 src = " http://code . jquery . com/jquery-1 . 11 . 1 . min . js "></脚本>
> <脚本 src = " http://code . jquery . com/mobile/1 . 4 . 5/jquery . mobile-1 . 4 . 5 . min . js "></脚本>

我们将使用不同类型的 ui 类和类型来组成标记按钮。

**示例 1:** 我们将使用带有 *class="ui-btn ui-mini"* 的锚点标签来制作按钮。

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
        <h4>Mini Anchor using jQuery Mobile</h4>
    </center>
    <a href="https://www.geeksforgeeks.org/" 
       class="ui-btn ui-mini">
       Mini Anchor
    </a>
</body> 

</html> 
```

**输出:**

![](img/9fe6ac4cb2c9cc8bf63149f791ceae1c.png)

**示例 2:** 我们将使用带有 *class="ui-btn ui-mini"* 的按钮标签。

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
        <h4>Mini buttons using jQuery Mobile</h4>
    </center>

    <button class="ui-btn ui-mini" id="gfg">
        Mini Button
    </button>
</body> 

</html> 
```

**输出:**

![](img/642d1d1709707e6dcd14cf5b336c983d.png)