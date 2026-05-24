# 引导中带有下拉列表的药丸

> Original: [https://www.geeksforgeeks.org/pills-with-dropdowns-in-bootstrap/](https://www.geeksforgeeks.org/pills-with-dropdowns-in-bootstrap/)

[**Bootstrap**](https://www.geeksforgeeks.org/bootstrap-4-introduction/)为改进内容导航提供了各种选项。 Bootstrap 下拉菜单是可切换的菜单，用于显示与 JavaScript 插件交互的数据列表。 我们可以通过单击来切换列表。 此外，我们还可以使用带有引导菜单下拉菜单的引导组件药丸作为药丸，使其能够显示。

我们使用*.nav-pilles*类来显示引导菜单选项，比如药丸。 我们需要将*.nav-pills*类添加到<ul>元素中，以便显示引导菜单选项(如 Pilles)。 下面是在 bootstrap 中使用下拉菜单实现 Pill 的过程。

**引导下拉实现药丸分步指南：**

**步骤 1：**在所有其他样式表之前将 Bootstrap 和[jQuery CDN](https://www.geeksforgeeks.org/how-to-add-jquery-code-to-html-file/)包含到<head>标记中，以加载 CSS。

> <link rel="”stylesheet”" href="”https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.min.css”">
> <脚本 src=”https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js”></脚本>
> <脚本 src=”https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/js/bootstrap.min.js”></脚本>和

步骤 2：在<ul>标记中的*.nav*类之后添加*.nav-pilles*类

```html
<ul class="nav nav-pills">
    <li class="active"><a href="#">Home</a></li>
    <li class="dropdown">
      <a class="dropdown-toggle" data-toggle="dropdown" href="#">
          Menu 1 <span class="caret"></span>
      </a>
      <ul class="dropdown-menu">
        <li><a href="#">Submenu 1-1</a></li>
        <li><a href="#">Submenu 1-2</a></li>
        <li><a href="#">Submenu 1-3</a></li>
      </ul>
    </li>
    <li><a href="#">Menu 2</a></li>
    <li><a href="#">Menu 3</a></li>
 </ul>
```

现在，我们已经成功地使用 PILES 实现了引导下拉。

**字体代码：**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Bootstrap Dropdown with Pills</title>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <!--Include bootstrap , CSS and jQuery CDN-->
    <link
      rel="stylesheet"
      href=
"https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.min.css"/>
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js">
    </script>
    <script src=
"https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/js/bootstrap.min.js">
    </script>
  </head>
  <body>
    <div class="container">
      <h3>Pills With Dropdown Menu</h3>

      <!--Include .nav-pills class after
          .nav class in <ul> tag-->
      <ul class="nav nav-pills">
        <li class="active"><a href="#">Home</a></li>
        <!--Include dropdown list here-->
        <li class="dropdown">
          <a class="dropdown-toggle"
            data-toggle="dropdown" href="#">
            Menu 1
            <span class="caret"></span>
          </a>
          <ul class="dropdown-menu">
            <li><a href="#">Submenu 1-1</a></li>
            <li><a href="#">Submenu 1-2</a></li>
            <li><a href="#">Submenu 1-3</a></li>
          </ul>
        </li>
        <li><a href="#">Menu 2</a></li>
        <li><a href="#">Menu 3</a></li>
      </ul>
    </div>
  </body>
</html>
```

发帖主题：Re：Колибри0.7.0

![](img/22ce55054e3413432b99e04f344014e3.png)

带有下拉菜单的药丸

**支持的浏览器：**

*   Google Chrome
*   微软边缘
*   火狐
*   歌剧 / 歌剧院 / 作品（opus 的复数）
*   野生动物考察 / 旅行 / 狩猎远征 / 旅行队