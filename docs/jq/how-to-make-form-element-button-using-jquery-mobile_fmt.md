# 如何使用 jQuery Mobile 制作表单元素按钮？

> 原文: [https://www.geeksforgeeks.org/how-to-make-form-element-button-using-jquery-mobile/](https://www.geeksforgeeks.org/how-to-make-form-element-button-using-jquery-mobile/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile 制作表单元素按钮。

## 方法
首先，添加项目所需的 jQuery Mobile 脚本。

> <link rel="stylesheet" href="http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css"/>
> <script src="http://code.jquery.com/jquery-1.11.1.min.js"></script>
> <script src="http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js"></script>

## 例 1

### HTML

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
            Form element button 
            using jQuery Mobile
        </h4>
    </center>

<a href="https://www.geeksforgeeks.org/" 
        data-role="button" data-theme="b">
        Click!
    </a>

<input type="button" value="Form element button"
        data-icon="arrow-l" data-theme="a">
</body>

</html>
```

**输出:**

![](img/c9755f46f4472d3f2734e16d578a9a55.png)

## 例 2

### HTML

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
            Form element button 
            using jQuery Mobile
        </h4>
    </center>

<button id="gfg" data-role="button" 
        data-theme="b">
        Click!
    </button>

<input type="button" 
        value="Form element button" 
        data-icon="arrow-l" data-theme="a">
</body>

</html>
```

**输出:**

![](img/c9755f46f4472d3f2734e16d578a9a55.png)