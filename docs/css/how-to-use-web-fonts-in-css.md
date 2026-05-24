# 如何在 CSS 中使用网页字体？

> 原文:[https://www.geeksforgeeks.org/how-to-use-web-fonts-in-css/](https://www.geeksforgeeks.org/how-to-use-web-fonts-in-css/)

在设计网页时，开发人员根据文本所代表的内容和最适合的字体使用不同的字体。每个系统都带有一些预安装的字体，称为系统字体。由于这些是有限的，人们可能会遇到需要使用不同于预安装字体的字体。在本文中，我们将讨论如何在 CSS 中使用网页字体。使用网络字体允许开发人员使用字体，而无需将这些字体下载或安装到他们的系统中。

**方法 1:** 如果您希望使用可通过 [<u>CDN</u>](https://www.geeksforgeeks.org/what-is-a-content-distribution-network-and-how-does-it-work/) 获得的字体(例如 [<u>谷歌字体</u>](https://fonts.google.com) )，那么您可以简单地选择所需的字体系列并使用 *<链接>* 标记或*@导入*规则。

**示例:**假设我们希望使用谷歌字体中的字体系列“矫正”，那么我们的 HTML 代码应该如下所示。

## 超文本标记语言

```html
<!DOCTYPE html>
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8" />

    <!-- This line defines the css styles file to be used -->
    <link rel="stylesheet" href="css/styles.css" />

    <!-- This is the link tag that needs to be 
         defined so that we can use the font -->
    <link href=
"https://fonts.googleapis.com/css2?family=Redressed&display=swap"
          rel="stylesheet"/>
    <style>
      #mainh1 {
        color: green;
        font-family: "Redressed", cursive;
      }
    </style>
  </head>
  <body>
    <h1 id="mainh1">GeeksforGeeks</h1>
  </body>
</html>
```

**输出:**

![](img/208c297c760fc9427c1b1ee10d3b5681.png)

在这里，我们也可以在我们的 CSS 中使用*@导入*规则。然后 CSS 文件会是这样的。

> @ import URL(' https://fonts . googleapis . com/css2？family = rechared & display = swap’)；
> 
> #mainh1{
> 颜色:绿色；
> 字体-家族:“重过”，草书；

**注意:**现在我们的 HTML 中不需要字体的<链接>标签。我们将在两种方法中获得相同的输出。

**方法二:**找到想要的字体后，我们也可以在我们的 CSS 文件开头使用 *@font-face* 。假设我们有字体 URL，并且我们想在我们的项目中使用它，那么我们可以将以下代码块添加到我们的 CSS 中:

```html
@font-face {
  font-family: "exampleFont";
  src: fontUrl("exampleFont.woff");
}
```

为了使用这种字体，我们可以简单地为所有我们希望以这种字体显示的元素定义字体系列部分。

**示例:**现在我们将使用相同的字体，即“矫正”但使用 *@font-face* 。我们的 HTML 代码如下所示:

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8" />
    <style>
      @font-face {
        font-family: exampleFont;
        src: url(Redressed-Regular.ttf);
      }

      #mainh1 {
        color: green;
        font-family: exampleFont;
      }
    </style>
  </head>
  <body>
    <h1 id="mainh1">GeeksforGeeks</h1>
  </body>
</html>
```

**注意:**你需要定义字体相对于它在你的网络服务器中的位置的路径。这里我们将字体文件保存在与我们的 HTML 代码相同的目录中，因此字体文件名是直接写的。

**输出:**
![](img/208c297c760fc9427c1b1ee10d3b5681.png)