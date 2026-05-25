# 如何使用 jQuery Mobile 创建仅图标定位图标？

> 原文: [https://www.geeksforgeeks.org/how-to-create-icon-only-positioning-icon-using-jquery-mobile/](https://www.geeksforgeeks.org/how-to-create-icon-only-positioning-icon-using-jquery-mobile/)

**jQuery Mobile** 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile 制作仅图标定位图标。

**方法:** 首先，添加项目所需的 jQuery Mobile 脚本。

> ```html
> <link rel="stylesheet" href="http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css">
> <script src="http://code.jquery.com/jquery-1.11.1.min.js"></script>
> <script src="http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js"></script>
> ```

### 例 1:

```html
<!DOCTYPE html> 
<html>
<head>
    <link rel="stylesheet" href="http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css"/>
    <script src="http://code.jquery.com/jquery-1.11.1.min.js"></script>
    <script src="http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js"></script>
</head>
<body> 
    <center>
        <h1>GeeksforGeeks</h1>
        <h4>
            Icon positioning Without text 
            using button tag in jQuery Mobile
        </h4>
    </center>
    <button id="gfg" data-role="button" 
            data-icon="delete" data-iconpos="notext">
        A button
    </button>
</body>
</html>
```

**输出:**

![](img/707ecab8588d726d13b6e10a52434b61.png)

### 例 2:

```html
<!DOCTYPE html> 
<html>
<head>
    <link rel="stylesheet" href="http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css"/>
    <script src="http://code.jquery.com/jquery-1.11.1.min.js"></script>
    <script src="http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js"></script>
</head>
<body> 
    <center>
        <h1>GeeksforGeeks</h1>
        <h4>Icon positioning Without text 
            using anchor tag in jQuery Mobile
        </h4>
    </center>
    <a href="https://www.geeksforgeeks.org/" 
       data-role="button" data-icon="delete" 
       data-iconpos="notext">
       An Anchor
    </a>
</body>
</html>
```

**输出:**

![](img/d1723ae5fad53d744950f3d31a9c9e7c.png)