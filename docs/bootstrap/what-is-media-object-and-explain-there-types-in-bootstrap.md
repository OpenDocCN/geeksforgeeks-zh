# 什么是媒体对象，说明 Bootstrap 中有哪些类型？

> 原文:[https://www . geesforgeks . org/什么是媒体对象和解释引导中的类型/](https://www.geeksforgeeks.org/what-is-media-object-and-explain-there-types-in-bootstrap/)

在本文中，我们将了解引导媒体对象，这有助于将媒体放在文本旁边。此外，我们将通过示例了解使用文本媒体的各种方式及其实现。媒体对象是引导组件，有助于在引导中构建重复设计，其中一些媒体以左对齐或右对齐的方式与不环绕媒体的文本内容一起放置。媒体对象需要两个引导类来包装**。媒体**和**。媒体-正文**它周围的内容。

我们将使用[引导 CDN](https://getbootstrap.com/docs/4.6/getting-started/introduction/) 链接将它们导入到 HTML 文件中。

> <rel = "样式表"链接 href = " https://cdn . jsdelivr . net/NPM/bootstrap @ 4 . 6 . 0/dist/CSS/bootstrap . min . CSS "完整性= " sha 384-b0vp 5 xmatw 1+K9 krqqrjvtumqwqw0npezvf 6 l/z6n NJ 3 ou ofufpcuquququququqouq 2+l " cross origin = " anonymous "/"
> 
> <src = " https://cdn . jsdelivr . net/NPM/bootstrap @ 5 . 1 . 3/dist/js/bootstrap . bundle . min . js "完整性= " sha 384-ka 7sk 0 Gln 4 gmtz 2 mlqnikt 1 wx gyusg+omhup+ilrh 9 senbo 0 lrn 5q+8nbtov 4+1p " cross origin = " anonymous ">

添加所需的 CDN 链接后，我们将使用下面的简单代码将媒体对象添加到我们的 HTML 文件中:

```html
<div class="media"> 
    <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20211025131754/GFGlogo2.jpg" 
         class="align-self-end mr-3" 
         alt="img" />
    <div class="media-body">
        <h5 class="mt-0">Media heading</h5>
        <p>
            Geeksforgeeks platform has been designed 
            for every geek wishing to expand their 
            knowledge, share their knowledge and is 
            ready to grab their dream job. 
        </p>
    </div>
</div>
```

**示例:**此示例描述了简单的*媒体* & *媒体-正文*对象。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" 
          content="IE=edge">
    <meta name="viewport" 
          content="width=device-width, 
                   initial-scale=1.0">
    <link rel="stylesheet" 
          href=
"https://cdn.jsdelivr.net/npm/bootstrap@4.6.0/dist/css/bootstrap.min.css" 
          integrity=
"sha384-B0vP5xmATw1+K9KRQjQERJvTumQW0nPEzvF6L/Z6nronJ3oUOFUFpCjEUQouq2+l" 
          crossorigin="anonymous">
    <title>Media Object</title>
</head>

<body>

  <!--Adding media class-->
    <div class="media"> 
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20211025131754/GFGlogo2-300x207.jpg" 
             class="mr-3" 
             alt="img">

      <!--Adding media-body class-->
        <div class="media-body">
            <h5 class="mt-0">Media heading</h5>
            <p>
                Geeksforgeeks platform has been 
                designed for every geek wishing 
                to expand their knowledge, share 
                their knowledge and is ready to 
                grab their dream job.
            </p>
        </div>
    </div>
</body>

</html>
```

**输出:**

![](img/0b9347f037b91600effb32d51da1996b.png)

示例媒体对象

引导数据库中有不同类型的媒体对象。

**嵌套媒体对象:**我们可以在 Bootstrap 内部制作嵌套媒体对象。要制作嵌套的媒体对象，我们必须在。媒体-身体类。在嵌套媒体对象中。媒体可以放在父媒体对象的内部。媒体-身体类。

**语法:**

```html
<div class="media-left">
    <img src="url">
    <div class="media-left">
        Content 
    </div>
</div>
```

**示例**:本示例描述了*嵌套媒体*身体对象。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" 
          content="IE=edge">
    <meta name="viewport" 
          content="width=device-width, 
                   initial-scale=1.0">
    <link rel="stylesheet" 
          href=
"https://cdn.jsdelivr.net/npm/bootstrap@4.6.0/dist/css/bootstrap.min.css" 
          integrity=
"sha384-B0vP5xmATw1+K9KRQjQERJvTumQW0nPEzvF6L/Z6nronJ3oUOFUFpCjEUQouq2+l" 
          crossorigin="anonymous">
    <title>Media Object</title>
</head>

<body>

  <!--media class -->
    <div class="media"> 
      <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20211025131754/GFGlogo2-300x207.jpg" 
           class="mr-3" 
           alt="img">

      <!--media-body class -->
      <div class="media-body">
          <h5 class="mt-0">Media heading</h5>
          <p>
              Geeksforgeeks platform has been 
              designed for every geek wishing 
              to expand their knowledge, share 
              their knowledge and is ready to 
              grab their dream job.
          </p>

          <!--Nested media class -->
          <div class="media"> 
              <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20211025131754/GFGlogo2-300x207.jpg" 
                  class="mr-3" alt="img">

              <!--Nested media-body class -->
              <div class="media-body">
                  <h5 class="mt-0">Media heading</h5>
                  <p>
                      Geeksforgeeks platform has been 
                      designed for every geek wishing 
                      to expand their knowledge, share 
                      their knowledge and is ready to 
                      grab their dream job.
                  </p>

                  <!--Nested media class -->
                  <div class="media"> 
                      <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20211025131754/GFGlogo2-300x207.jpg" 
                           class="mr-3" 
                           alt="img">

                      <!--Nested media-body class -->
                        <div class="media-body">
                            <h5 class="mt-0">Media heading</h5>
                            <p>
                              Geeksforgeeks platform has been 
                              designed for every geek wishing 
                              to expand their knowledge, share 
                              their knowledge and is ready to 
                              grab their dream job.
                            </p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</body>

</html>
```