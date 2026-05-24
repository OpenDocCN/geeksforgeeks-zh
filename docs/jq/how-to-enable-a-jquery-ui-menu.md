# 如何启用 jQuery UI 菜单？

> 原文:[https://www . geesforgeks . org/如何启用-a-jquery-ui-menu/](https://www.geeksforgeeks.org/how-to-enable-a-jquery-ui-menu/)

jQuery UI 由 GUI 小部件、视觉效果和使用 jQuery、CSS 和 HTML 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。jQuery UI 菜单是一个 菜单，用于鼠标和键盘交互在页面之间导航*。* 在本文中，我们将展示如何在 jQuery UI 中启用菜单。

**语法:**

```html
$(".selector").menu( "enable" );
```

**方法:**首先，添加项目所需的 jQuery UI 脚本。

> <link href="“https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css”" rel="“stylesheet”">

**Example 1:** In this example, we will be creating and enabling the menu for our purposes. 

## 超文本标记语言

```html
<!doctype html>
<html lang = "en">
   <head>
      <meta charset = "utf-8">
      <link href = 
"https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css"
         rel = "stylesheet">
      <script src = "https://code.jquery.com/jquery-1.10.2.js"></script>

      <script src = "https://code.jquery.com/ui/1.10.4/jquery-ui.js">
      </script>

      <style>
         .ui-menu {
            width: 200px;
         }
      </style>

      <script>
         $(function() {
            $( "#gfg" ).menu();
            $( "#gfg" ).menu("enable");
         });
      </script>
   </head>

   <body>
      <h1>jQuery UI | enable menu </h1>
      <ul id = "gfg">
         <li><a href = "https://www.geeksforgeeks.org/">1st</a></li>
         <li><a href = "https://www.geeksforgeeks.org/">2nd</a></li>
         <li><a href = "https://www.geeksforgeeks.org/">3rd</a></li>
         <li><a href = "https://www.geeksforgeeks.org/">2th</a></li>
         <li><a href = "https://www.geeksforgeeks.org/">5th</a></li>
      </ul>
   </body>
</html>
```

**输出:**

![](img/2f2c4ffdd79a53c790372c86f5a6f214.png)