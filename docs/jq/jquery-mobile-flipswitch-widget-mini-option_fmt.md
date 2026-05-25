# jQuery Mobile Flipswitch Widget Mini Option

> 原文：[https://www.geeksforgeeks.org/jquery-mobile-flipswitch-widget-mini-option/](https://www.geeksforgeeks.org/jquery-mobile-flipswitch-widget-mini-option/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile Flipswitch Widget 的 `mini` 选项来显示紧凑的 flipswitch Widget。如果该选项值设置为 `true`，它将显示按钮的紧凑版本，即垂直高度最小。

## 语法

```html
$( ".selector" ).flipswitch({
    mini: boolean
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
                mini: true
            });
        });
    </script>
</head>

<body>
    <div data-role="page" id="page1">
        <div data-role="header">
            <h1>GeeksforGeeks</h1>
            <h3>jQuery Mobile Flipswitch Widget mini Option</h3>
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

![](img/c047c5d80cd67c762a480ccfc8307dc2.png)

## 参考

[https://api.jquerymobile.com/flipswitch/#option-mini](https://api.jquerymobile.com/flipswitch/#option-mini)