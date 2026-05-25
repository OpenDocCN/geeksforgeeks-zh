# jQuery Mobile Selectmenu Widget hidePlaceholderMenuItems 选项

> 哎哎哎: [https://www.geeksforgeeks.org/jquery-mobile-selectmenu-widget-hideplaceholdermenuitems-option/](https://www.geeksforgeeks.org/jquery-mobile-selectmenu-widget-hideplaceholdermenuitems-option/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile Selectmenu Widget `hidePlaceholderMenuItems` 选项来检查占位符菜单项是否隐藏。它接受布尔类型值，默认值为真。

## 语法

```javascript
$( ".selector" ).selectmenu({
    hidePlaceholderMenuItems: boolean
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
                hidePlaceholderMenuItems: true
            });
        });
    </script>
</head>

<body>
    <div data-role="page" id="page1">
        <center>
            <div data-role="header">
                <h1>GeeksforGeeks</h1>
                <h3>jQuery Mobile Selectmenu Widget hidePlaceholderMenuItems Option</h3>
            </div>
        </center>
        <div role="main" class="ui-content">
            <label for="GFG" class="select">
                GeeksforGeeks Courses:
            </label>
            <select name="GFG" id="GFG">
                <option value="" disabled selected hidden>Choose One...</option>
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

![](img/9d31d36c4a595b060a4489983bc8411e.png)

## 参考

[https://api.jquerymobile.com/selectmenu/#option-hidePlaceholderMenuItems](https://api.jquerymobile.com/selectmenu/#option-hidePlaceholderMenuItems)