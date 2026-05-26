# jQuery 用户界面滑块禁用选项

> 原文:[https://www . geesforgeks . org/jquery-ui-slider-disabled-option/](https://www.geeksforgeeks.org/jquery-ui-slider-disabled-option/)

jQuery UI 由 GUI 小部件、视觉效果和使用 jQuery、CSS 和 HTML 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。jQuery UI 通过滑块小部件为我们提供了一个滑块控件。滑块帮助我们使用给定的范围获得某个值。在本文中，我们将看到如何禁用滑块。当设置为*真*时，*禁用*选项将禁用滑块。

**语法:**

```html
$(".selector").slider(
   { disabled : true }
);
```

**参数:**该选项接受一个参数，如下所述:

*   **布尔值:**如果设置为*真*，滑块将被禁用。默认情况下，该值为*假。*

**CDN 链接:**首先，添加项目所需的 jQuery UI 脚本。

> <link href="“https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css”" rel="“stylesheet”">
> <脚本 src = " https://code . jquery . com/jquery-1 . 10 . 2 . js "></脚本>
> <脚本 src = " https://code . jquery . com/ui/1 . 10 . 4/jquery-ui . js "></脚本>

**示例 1:** 在本例中，我们将使用布尔值作为*真*。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <link href=
"https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css"
      rel="stylesheet"/>
    <script src=
"https://code.jquery.com/jquery-1.10.2.js">
    </script>
    <script src=
"https://code.jquery.com/ui/1.10.4/jquery-ui.js">
    </script>

    <script>
      $(function () {
        $("#gfg").slider({ disabled: true });
      });
    </script>
  </head>

  <body>
    <h1>GeeksforGeeks</h1>
    <h2>jQuery UI | slider disabled option</h2>
    <div id="gfg"></div>
  </body>
</html>
```

**输出:**

![](img/cd2e736bd0c707bd37b83aaec582d93b.png)

**例 2:** 在本例中，我们将使用布尔值作为*假*。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <link href=
"https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css"
      rel="stylesheet"/>
    <script src=
"https://code.jquery.com/jquery-1.10.2.js">
    </script>
    <script src=
"https://code.jquery.com/ui/1.10.4/jquery-ui.js">
    </script>
    <script>
      $(function () {
        $("#gfg").slider({ disabled: false });
      });
    </script>
  </head>

  <body>
    <h1>GeeksforGeeks</h1>
    <h2>jQuery UI | slider disabled option</h2>
    <div id="gfg"></div>
  </body>
</html>
```

**输出:**

![](img/10f1b600e547d46e6722eaea294e3ed6.png)

**参考:**T2】https://api.jqueryui.com/slider/#option-disabled