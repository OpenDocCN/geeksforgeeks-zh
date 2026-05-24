# 如何在 Bootstrap 中设置垂直对齐？

> 原文:[https://www . geesforgeks . org/如何在引导中设置垂直对齐/](https://www.geeksforgeeks.org/how-to-set-vertical-alignment-in-bootstrap/)

垂直对齐在垂直对齐工具的帮助下，垂直更改元素的对齐方式。垂直对齐实用程序仅影响内联(显示在一行中)、内联块(显示为一行中的块)、内联表格和表格单元格(表格单元格中的元素)元素。垂直对齐是一个有响应的网页最基本的要求之一。这可以通过 CSS 来实现，但是 Bootstrap 库有一些专门为此目的而构建的类。在本文中，我们将学习 Bootstrap 中用于垂直对齐的可用类和方法。其他垂直对齐类请参考引导中的[垂直对齐和示例](https://www.geeksforgeeks.org/vertical-alignment-in-bootstrap-with-examples/)。

在这里，我们将讨论两个内置类:

*   使用类 ***对齐-物品-中心***
*   使用类 ***d-flex*** 与类 ***对齐-物品-居中***

让我们通过例子来理解这两个类。

**方法 1:** 使用类 ***对齐-物品-中心***

在 Bootstrap 5 中，如果我们想在中心垂直对齐一个

元素，我们可以通过在该 div 的包含元素上应用类*对齐-项目-中心*来实现。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8"/>
    <meta name="viewport" content="width=device-width, initial-scale=1" />

    <link
      rel="stylesheet"
      href=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css"/>

    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js">
    </script>
    <script src=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js">
    </script>
  </head>

  <body>
    <div class="container">
      <div
        class="row align-items-center bg-success text-light"
        style="min-height: 100vh">
        <div class="col-md-12">
          <h1>GeeksforGeeks</h1>
        </div>
      </div>
    </div>
  </body>
</html>
```

**输出:**

![](img/2f3918140de828096544957c380f028c.png)

**方法 2:** 使用类 ***d-flex*** 与类 ***对齐-物品-中心***

在 Bootstrap 5 中，如果我们想在包含元素的中间垂直对齐一个

元素，我们可以通过在该 div 的包含元素上应用类 *align-items-center* 和 *d-flex* 来实现。这里 *d-flex* 类的效果和*显示一样:flex；*CSS 中的属性。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8"/>
    <meta name="viewport" content="width=device-width, initial-scale=1"/>

    <link
      rel="stylesheet"
      href=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css"/>

    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js">
    </script>
    <script src=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js">
    </script>
  </head>

  <body>
    <div class="d-flex align-items-center" style="min-height: 100vh">
      <div class="box w-100 text-success">
        <h1>GeeksforGeeks</h1>
      </div>
    </div>
  </body>
</html>
```

**输出:**

![](img/007a77f6b4c780142eb2d2932c29516e.png)