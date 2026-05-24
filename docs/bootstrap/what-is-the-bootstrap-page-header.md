# 什么是 Bootstrap 页头？

> 原文:[https://www . geesforgeks . org/什么是引导页面标题/](https://www.geeksforgeeks.org/what-is-the-bootstrap-page-header/)

页眉用于在页面标题周围添加适当的间距，并在标题下添加水平线。这特别有助于一个网页，你可能有几个文章标题，需要一种方法来增加它们的区别。因为标题永远是观众的第一印象。因此，人们会希望他们的页面在页面顶部有一个好看的标题，并且标题可以很容易地突出显示。为此，网页开发人员使用了一个页眉，它在网页的标题周围增加了间距，并在标题下增加了一条水平线。

让我们看看逐步实现的方法。

**第一步:**将 Bootstrap 和 jQuery CDN 包含到 [<u><头></u>](https://www.geeksforgeeks.org/html-head-tag/) 标签之前，所有其他样式表加载我们的 CSS。

> <src = " https://Ajax . Google APIs . com/Ajax/libs/jquery/3 . 5 . 1/jquery . min . js "></script><src = " https://maxcdn . bootstracdn . com/bootstrap/3 . 4 . 1/脚本

**第二步:**用类容器在 HTML 体中添加 [<u>< div ></u>](https://www.geeksforgeeks.org/div-tag-html/) 标签。

**第三步:**要使用页眉，请将您的页眉包装在一个<分区>中，该分区的等级为**。页首**。

```html
<div class = "page-header"> </div>

```

**示例 1:** 在本例中，我们将看到如何使用带下划线标题的 Bootstrap 页面标题。

## index.html

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Example</title>
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
    <style>
      img {
        border-radius: 50%;
      }
    </style>
  </head>
  <body>
    <div class="container">
      <div class="page-header">
        <h1 style="color: green">Example Page Header</h1>
      </div>

      <p>This is a paragraph</p>

      <img
        src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png"
        alt="Flowers in Chania"
        width="460"
        height="345"/>
      <p>This is another text.</p>
    </div>
  </body>
</html>
```

**输出:**

![](img/bdccdf447c756b2943cfec2b3b02d1f2.png)

合适的间距和标题下的水平线

**示例 2:** 在本例中，我们将看到标题大小不同且没有下划线的页眉。

## index.html

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Example</title>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <link
      rel="stylesheet"
      href=
"https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css"/>
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.1.1/jquery.min.js">
    </script>
    <script src=
"https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js">
    </script>
  </head>
  <body>
    <div class="container">
      <div class="page-header">
        <h1 style="color: green">
          GeeksForGeeks
           <small> All In One</small>
        </h1>
      </div>

      <p>Extensive collection of questions ranging variety of topics</p>

      <p>All done by Experts</p>
    </div>
  </body>
</html>
```

**输出:**

![](img/cc86f02e36b44b5e3b6b729adac1ea56.png)

没有下划线的适当间距