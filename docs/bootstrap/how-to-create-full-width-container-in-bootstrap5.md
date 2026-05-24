# 如何在 bootstrap5 中创建全宽容器？

> 原文:[https://www . geeksforgeeks . org/如何创建全宽容器 in-bootstrap5/](https://www.geeksforgeeks.org/how-to-create-full-width-container-in-bootstrap5/)

引导容器是内容容器，用于对齐内容，为内容添加边距和填充。Bootstrap 有三个不同的容器类，即:

*   。容器
*   。容器流体
*   。容器-{断点}

容器的宽度因其类别而异。我们可以使用**在 Bootstrap5 中创建一个全宽容器。容器-流体“**级。它将所有屏幕尺寸中的容器宽度设置为 100%。这意味着容器横跨视口的整个宽度。

**语法:**

```html
<div class= ".container-fluid">
  ...
</div>  

```

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <link rel="stylesheet"
              href=
"https://stackpath.bootstrapcdn.com/bootstrap/5.0.0-alpha1/css/bootstrap.min.css"
              integrity=
"sha384-r4NyP46KrjDleawBgD5tp8Y7UzmLA05oM1iAEQ17CSuDqnUK2+k9luXQOfXJCJ4I"
              crossorigin="anonymous" />

        <style>
            .gfg {
                background-color: green;
                color: white;
                text-align: center;
            }
        </style>
    </head>

    <body>
        <div class="container-fluid gfg">
            <h2>GeeksforGeeks</h2>
        </div>
    </body>
</html>
```

**输出:**

![](img/9f347020a272099b2a7ef480ca3e9306.png)