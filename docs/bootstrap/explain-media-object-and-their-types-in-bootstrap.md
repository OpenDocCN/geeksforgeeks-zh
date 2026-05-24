# 在引导

中解释媒体对象及其类型

> 原文:[https://www . geesforgeks . org/explain-media-object-and-type-in-bootstrap/](https://www.geeksforgeeks.org/explain-media-object-and-their-types-in-bootstrap/)

在本文中，我们将了解引导媒体对象，这有助于将媒体放在文本旁边。此外，我们将通过示例了解使用文本媒体的各种方式及其实现。引导媒体对象可以用于放置一些内容，此外还有一些媒体，有助于使网站内容吸引人和有趣。媒体对象(如图像或视频)可以以简单有效的方式对齐到某些内容的左侧或右侧。引导媒体对象用于将一些数据放在内容旁边，以构建内容的复杂和递归组件。

媒体对象的两个主要类别是:

*   。媒体
*   。媒体-正文

**进场:**

*   将子元素包装在 ***中。**传媒*班。
*   然后使用 ***< img >*** 标签来指定像图像这样的媒体内容。
*   然后在里面。 ***媒体-正文*** 类，添加媒体内容。
*   我们也可以在父级 ***中创建嵌套的媒体内容。**媒体-身体*类。

要在网站中包含引导媒体对象，我们需要执行以下步骤:

**步骤 1:** 在 HTML <头>部分包含 Bootstrap CSS 来加载样式表。

> <link rel="”stylesheet”" href="”https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css”" integrity="”sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm”" crossorigin="”anonymous”">

添加引导 JavaScript 插件和依赖项。

> <src 脚本= " https://cdnjs . cloudflare . com/Ajax/libs/popper . js/1 . 12 . 9/UMD/popper . min . js "完整性= " sha 384-apnbgh 9b+y1qktv 3rn 7mgpx Hu 9k/scqsap 7 hubx 39j7 fakfpskvxusfa 0b 4q " cross origin = " anonymous "

**步骤 2:** 我们可以直接复制[官方](https://getbootstrap.com/docs/4.3/getting-started/introduction/)自举文档中给出的[自举入门模板](https://getbootstrap.com/docs/4.3/getting-started/introduction/#starter-template)。

## 超文本标记语言

```html
<!doctype html>
<html lang="en">
<head>

    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" 
          content="width=device-width, 
                   initial-scale=1, 
                   shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" 
          href=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css" 
          integrity=
"sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm" 
          crossorigin="anonymous">
    <title>Hello, world!</title>
</head>

<body>
    <h1>Hello, world!</h1>

    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->

    <script src=
"https://code.jquery.com/jquery-3.2.1.slim.min.js" 
            integrity=
"sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN" 
            crossorigin="anonymous">
    </script>
    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.9/umd/popper.min.js" 
            integrity=
"sha384-ApNbgh9B+Y1QKtv3Rn7W3mgPxhU9K/ScQsAP7hUibX39j7fakFPskvXusvfa0b4Q" 
            crossorigin="anonymous">
    </script>
    <script src=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js" 
            integrity=
"sha384-JZR6Spejh4U02d8jOt6vLEHfe/JQGiRRSQQxSfFWpi1MquVdAyjUar5+76PVCmYl" 
            crossorigin="anonymous">
    </script>
</body>
</html>
```

我们将使用入门模板，使用引导媒体对象构建网页。

*   **基本媒体对象:**我们将使用****。媒体类**添加到容器元素中，并用**将媒体内容放入子容器中。媒体-正文**类。**

****示例 1:** 该示例说明了引导媒体对象的使用。**

## **超文本标记语言**

```html
<!doctype html>
<html lang="en">
<head>

    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" 
          content="width=device-width, 
                   initial-scale=1, 
                   shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" 
          href=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css" 
          integrity=
"sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm" 
          crossorigin="anonymous">
    <title>GeeksforGeeks!</title>
</head>

<body>
    <h1 style="color: green;">GeeksforGeeks!</h1>
    <div class="media"> 
        <img class="mr-3" 
             src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png" 
             width="100" 
             height="100" 
             alt="Alternate image">
        <div class="media-body">
            <h4 class="mt-0">
                Media heading Example1
            </h4> 
            GeeksforGeeks Bootstrap Media Content 
        </div>
    </div>
</body>
</html>
```