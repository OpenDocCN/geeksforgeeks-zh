# 如何使用 jQuery Mobile 制作全屏工具栏？

> 原文：[https://www.geeksforgeeks.org/how-to-make-fullscreen-toolbars-using-jquery-mobile/](https://www.geeksforgeeks.org/how-to-make-fullscreen-toolbars-using-jquery-mobile/)

`jQuery Mobile` 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 `jQuery Mobile` 制作全屏工具栏。

## 方法
首先，添加项目所需的 `jQuery Mobile` 脚本。
```html
<link rel="stylesheet" href="http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css">
```

## 示例 1：创建全屏底部工具栏
```html
<!DOCTYPE html>
<html>
<head>
    <link rel="stylesheet" href="http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css" />
    <script src="http://code.jquery.com/jquery-1.11.1.min.js"></script>
    <script src="http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js"></script>
</head>
<body>
    <center>
        <h1>GeeksforGeeks</h1>
        <h4>fullscreen toolbar using jQuery Mobile</h4>
    </center>
    <div data-role="footer" data-position="fixed" data-fullscreen="true">
        <h1>Fixed footer!</h1>
    </div>
</body>
</html>
```

**输出：**
![](img/f3cd43a3acadccb637ecdf8d17236340.png)

## 示例 2：创建全屏顶部工具栏
```html
<!DOCTYPE html>
<html>
<head>
    <link rel="stylesheet" href="http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css" />
    <script src="http://code.jquery.com/jquery-1.11.1.min.js"></script>
    <script src="http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js"></script>
</head>
<body>
    <center>
        <h1>GeeksforGeeks</h1>
        <h4>fullscreen toolbar using jQuery Mobile</h4>
    </center>
    <div data-role="header" data-position="fixed" data-fullscreen="true">
        <h1>Fixed Header!</h1>
    </div>
</body>
</html>
```

**输出：**
![](img/d6aa6270fc83c3ba8ec4cd62b2903af0.png)