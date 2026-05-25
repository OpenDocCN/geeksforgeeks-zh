# jQuery Mobile Flipswitch Widget Defaults Option

> 原文：[https://www.geeksforgeeks.org/jquery-mobile-flipswitch-widget-defaults-option/](https://www.geeksforgeeks.org/jquery-mobile-flipswitch-widget-defaults-option/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用带有 `true` 值的 jQuery Mobile `flipswitch` widget `defaults` 选项来设置其他具有默认值的 Widget 选项，并使 Widget 自动增强代码省略从数据属性中检索选项值的步骤。它接受布尔类型值，默认值为 `false`。

## 语法

```html
$( ".selector" ).flipswitch({
    defaults: boolean
});
```

## CDN 链接

首先，添加项目所需的 jQuery Mobile 脚本。

> <link rel="stylesheet" href="//code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css">
> <script src="//code.jquery.com/jquery-1.10.2.min.js"></script>
> <script src="//code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js"></script>

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
                defaults: true
            });
        });
    </script>
</head>

<body>
    <div data-role="page" id="page1">
        <div data-role="header">
            <h1>GeeksforGeeks</h1>
            <h3>jQuery Mobile Flipswitch Widget defaults Option</h3>
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

![](img/c4aded7494e11d94aa129f825fa27c9f.png)

## 参考

[https://api.jquerymobile.com/flipswitch/#option-defaults](https://api.jquerymobile.com/flipswitch/#option-defaults)