# jQuery Mobile Selectmenu Widget Corners 选项

> 原文链接: [https://www.geeksforgeeks.org/jquery-mobile-selectmenu-widget-corners-option/](https://www.geeksforgeeks.org/jquery-mobile-selectmenu-widget-corners-option/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应式内容。
在本文中，我们将使用 jQuery Mobile `selectmenu` Widget 的 `corners` 选项来设置边框半径。它接受布尔类型值，默认值为 `true`。

## 语法

```html
$( ".selector" ).selectmenu({
    corners: boolean
});
```

## CDN 链接

首先，添加项目所需的 jQuery Mobile 脚本。

```html
<script src="//code.jquery.com/jquery-3.2.1.min.js"></script>
<script src="//code.jquery.com/mobile/1.5.0-alpha.1/jquery.mobile-1.5.0-alpha.1.min.js"></script>
```

## 示例

```html
<!doctype html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="stylesheet" href="//code.jquery.com/mobile/1.5.0-alpha.1/jquery.mobile-1.5.0-alpha.1.min.css">
    <script src="//code.jquery.com/jquery-3.2.1.min.js"></script>
    <script src="//code.jquery.com/mobile/1.5.0-alpha.1/jquery.mobile-1.5.0-alpha.1.min.js"></script>
    <script>
        $(document).ready(function () {
            $("#GFG").selectmenu({
                corners: false
            });
        });
    </script>
</head>

<body>
    <div data-role="page" id="page1">
        <center>
            <div data-role="header">
                <h1>GeeksforGeeks</h1>
                <h3>jQuery Mobile Selectmenu Widget corners Option</h3>
            </div>
        </center>
        <div role="main" class="ui-content">
            <label for="GFG" class="select">
                GeeksforGeeks Courses:
            </label>
            <select name="GFG" id="GFG">
                <option value="C">C Programming</option>
                <option value="CPP">C++ Programming</option>
                <option value="JAVA">Java Programming</option>
                <option value="overnight">Python Programming</option>
                <option value="WEB">Web Development</option>
            </select>
        </div>
    </div>
</body>

</html>
```

## 输出

![](img/4c5e49a9d9ed262513125e98c4f6f397.png)

当 `corners` 选项设置为 `false` 时，我们得到如下输出，通过该输出您可以很好地注意到拐角的差异。

![](img/589a7ad0188c6bf5cfeee2572a039324.png)

当 `corners` 设置为 `true` 时

## 参考

[https://api.jquerymobile.com/selectmenu/#option-corners](https://api.jquerymobile.com/selectmenu/#option-corners)