# 如何使用 jQuery Mobile 创建搜索输入？

> 原文：[`https://www.geeksforgeeks.org/how-to-create-a-search-input-using-jquery-mobile/`](https://www.geeksforgeeks.org/how-to-create-a-search-input-using-jquery-mobile/)

[`jQuery Mobile`](https://jquerymobile.com/) 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 [`jQuery Mobile`](https://jquerymobile.com/) 创建一个 [`search input`](https://api.jquerymobile.com/searchinput/)。

## 进场

首先，我们添加项目所需的 [`jQuery Mobile`](https://jquerymobile.com/) 脚本。

```html
<link rel="stylesheet" href="http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css">
<script src="http://code.jquery.com/jquery-1.11.1.min.js"></script>
<script src="http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js"></script>
```

我们现在可以开始创建基于 [`jQuery Mobile`](https://jquerymobile.com/) 的 [`search input`](https://api.jquerymobile.com/searchinput/)。

## 示例

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
            Design a Search Input using jQuery Mobile
        </h4>
        <form style="width: 50%;">
            <label for="searchArea">
                Search Content
            </label>

<input type="search" name="searchArea" 
                id="searchArea" value="" 
                placeholder="Search Text...">
        </form>
    </center>
</body>

</html>
```

## 输出

![](img/2c3810210c88b499b4ff0809348ecdd5.png)