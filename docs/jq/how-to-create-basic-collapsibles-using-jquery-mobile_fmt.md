# 如何使用 jQuery Mobile 创建基本可折叠组件？

> 原文：[https://www.geeksforgeeks.org/how-to-create-basic-collapsibles-using-jquery-mobile/](https://www.geeksforgeeks.org/how-to-create-basic-collapsibles-using-jquery-mobile/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile 制作一个基本的可折叠文件。

## 方法

首先，添加项目所需的 jQuery Mobile 脚本。

```html
<link rel="stylesheet" href="http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css">
<script src="http://code.jquery.com/jquery-1.11.1.min.js"></script>
<script src="http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js"></script>
```

## 示例

### 超文本标记语言

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
            Basic collapsible 
            using jQuery Mobile
        </h4>
    </center>

<div data-role="collapsible">
        <h4>GeeksforGeeks</h4>

<p>This content is collapsible</p>
    </div>
</body>

</html>
```

## 输出

![](img/8550254f3ae4f7a1f472c33cb6b140bd.png)