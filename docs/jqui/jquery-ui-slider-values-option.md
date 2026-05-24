# jQuery 用户界面滑块值选项

> 原文:[https://www . geesforgeks . org/jquery-ui-slider-values-option/](https://www.geeksforgeeks.org/jquery-ui-slider-values-option/)

jQuery UI 由 GUI 小部件、视觉效果和使用 jQuery、CSS 和 HTML 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。 jQuery UI 通过滑块小部件为我们提供了一个滑块控件。滑块帮助我们使用给定的范围获得某个值。在本文中，我们将看到如何在滑块中设置 **值** 选项。 **值** 选项将为滑块的滑块手柄设置一组值。

**语法:**

```html
$(".selector").slider(
   { values : array}
);
```

**参数:**如下所述，该选项接受一个值。

*   **数组:** T 要设置的滑块手柄的值数组。默认情况下，该值为**空值**。

**方法:**首先，添加项目所需的 jQuery UI 脚本。

> <link href="“https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css”" rel="“stylesheet”">

**示例 1:** 在本例中，我们将使用数组值作为 5，10，15。

## 超文本标记语言

```html
<!doctype html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <link href=
"https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css"
        rel="stylesheet">
    <script src="https://code.jquery.com/jquery-1.10.2.js"></script>

    <script src="https://code.jquery.com/ui/1.10.4/jquery-ui.js">
    </script>

    <script>
        $(function() {
            $("#gfg").slider({
                values: [5, 10, 15]
            });
        });
    </script>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h2>jQuery UI | slider values option</h2>
    <div id="gfg"></div>
</body>

</html>
```

**输出:**

![](img/e60b802c7d26942b60f25c303c37ec4d.png)

**示例 2:** 在本例中，我们将使用数组值作为 12，18。

## 超文本标记语言

```html
<!doctype html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <link href=
"https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css"
        rel="stylesheet">
    <script src="https://code.jquery.com/jquery-1.10.2.js"></script>

    <script src="https://code.jquery.com/ui/1.10.4/jquery-ui.js">
    </script>

    <script>
        $(function() {
            $("#gfg").slider({
                values: [12, 18]
            });
        });
    </script>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h2>jQuery UI | slider values option</h2>
    <div id="gfg"></div>
</body>

</html>
```

**输出:**

![](img/1998a3d7b206d9adda77fa12fe4bfc05.png)