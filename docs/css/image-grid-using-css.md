# 使用 CSS 的图像网格

> 原文:[https://www.geeksforgeeks.org/image-grid-using-css/](https://www.geeksforgeeks.org/image-grid-using-css/)

在本文中，我们将看到如何使用 HTML 和 CSS 创建钻石网格。我们将使用*位置*属性以网格形式对齐图像。

*   **HTML 部分代码:**在本节中，我们将创建一个网格结构。

    **进场:**

    1.  使用“ul”创建一个有序列表，并添加一个类容器。
    2.  用类名创建六个“li”标记。
    3.  包括一个带有类名 *bg* 的“div”标签。

    ## 超文本标记语言

    ```html
    <!DOCTYPE html>
    <html>
    <body>
     <!-- container for holding all images -->
    <ul class="container">
    <!-- all li for items -->
     <li class="item1">
        <div class="bg"></div>
      </li>
      <li class="item2">
        <div class="bg"></div>
      </li>
      <li class="item3">
        <div class="bg"></div>
      </li>
      <li class="item4">
        <div class="bg"></div>
      </li>
      <li class="item5">
        <div class="bg"></div>
      </li>
    </ul>
    </body>
    </html>
    ```