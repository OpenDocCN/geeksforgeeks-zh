# jQuery UI 工具提示 `destroy()` 方法

> 原文：[https://www.geeksforgeeks.org/jquery-ui-tooltips-destroy-method/](https://www.geeksforgeeks.org/jquery-ui-tooltips-destroy-method/)

jQuery UI 由 GUI 小部件、视觉效果和使用 jQuery、CSS 和 HTML 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。jQuery UI 工具提示小部件帮助我们添加新主题并允许自定义。在本文中，我们将看到如何在 jQuery UI 工具提示中使用 `destroy` 选项。`destroy` 选项用于销毁 jQuery UI 中的工具提示。

**语法：**

```html
$(".selector").tooltip("destroy");
```

**参数：** 此方法不接受任何参数。

**CDN 链接：** 首先，添加项目所需的 jQuery UI 脚本。

```html
<link href="https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css" rel="stylesheet">
<script src="https://code.jquery.com/jquery-1.10.2.js"></script>
<script src="https://code.jquery.com/ui/1.10.4/jquery-ui.js"></script>
```

**示例：** 以下示例演示了工具提示的 `destroy` 选项。一旦点击“click to destroy!”按钮时，它会销毁工具提示。

## HTML 示例

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <link
      href="https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css"
      rel="stylesheet"
    />
    <script src="https://code.jquery.com/jquery-1.10.2.js"></script>
    <script src="https://code.jquery.com/ui/1.10.4/jquery-ui.js"></script>

    <h1 style="color: green">GeeksforGeeks</h1>
    <h3>jQuery UI | Tooltip destroy method</h3>

    <script>
      $(function () {
        $("#gfgtt").tooltip({
          track: true,
        });
        $("#gfg").click(function () {
          $("#gfgtt").tooltip("destroy");
        });
      });
    </script>
  </head>

  <body>
    <input
      id="gfg"
      type="submit"
      name="GeeksforGeeks"
      value="click to destroy!"
    />
    <button id="gfgtt" title="GeeksforGeeks">Click here!</button>
  </body>
</html>
```

**输出：**

![](img/c87562f76d80ba5d1904b6f1fc909306.png)

**参考：** [https://api.jqueryui.com/tooltip/#method-destroy](https://api.jqueryui.com/tooltip/#method-destroy)