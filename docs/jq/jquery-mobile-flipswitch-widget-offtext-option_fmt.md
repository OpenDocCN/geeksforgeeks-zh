# jQuery Mobile Flipswitch Widget offText 选项

> 原文：[https://www.geeksforgeeks.org/jquery-mobile-flipswitch-widget-offtext-option/](https://www.geeksforgeeks.org/jquery-mobile-flipswitch-widget-offtext-option/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile Flipswitch Widget 的 `offText` 选项，在 flipswitch 处于“OFF”状态时设置其上的标签文本。它接受字符串类型值，默认值为“关”。

## 语法

```html
$( ".selector" ).flipswitch({
    offText: string
});
```

## CDN 链接

首先，添加项目所需的 jQuery Mobile 脚本。

```html
<link rel="stylesheet" href="//code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css">
<script src="//code.jquery.com/jquery-1.10.2.min.js"></script>
<script src="//code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js"></script>
```

## 示例

```html
<!doctype html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1">

    <link rel="stylesheet" href=
        "//code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css">

    <script src=
        "//code.jquery.com/jquery-1.10.2.min.js">
    </script>

    <script src=
        "//code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js">
    </script>

    <script>
        $(document).ready(function () {
            $("#GFG").flipswitch({
                offText: "GfG"
            });
        });
    </script>
</head>

<body>
    <div data-role="page" id="page1">
        <div data-role="header">
            <h1>GeeksforGeeks</h1>
            <h3>jQuery Mobile Flipswitch Widget offText Option</h3>
        </div>

        <div class="ui-field-contain">
            <form>
                <div data-role="fieldcontain">
                    <center>
                        <label for="GFG">
                            Flipswitch Checkbox:
                        </label>
                        <input type="checkbox" id="GFG" 
                            data-role="flipswitch">
                    </center>
                </div>
            </form>
        </div>
    </div>
</body>

</html>
```

## 输出

![](img/537bbd426ff2b61b9d94b1a450601d51.png)

## 参考

[https://api.jquerymobile.com/flipswitch/#option-offText](https://api.jquerymobile.com/flipswitch/#option-offText)