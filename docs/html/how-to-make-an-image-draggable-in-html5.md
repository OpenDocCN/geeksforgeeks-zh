# 如何在 HTML5 中制作可拖动的图像？

> 原文:[https://www . geesforgeks . org/如何制作图像-可拖动的 html5/](https://www.geeksforgeeks.org/how-to-make-an-image-draggable-in-html5/)

拖放是现代网站中非常常见且广泛使用的功能。它只是意味着用光标拖动图像，并将其放到任何其他地方。在本文中，我们将学习如何使用 HTML 5 制作可拖动的图像。

让任何 HTML5 元素包括图像都是可拖动的非常容易。我们借助[‘可拖动’](https://www.geeksforgeeks.org/html-draggable-attribute/)属性。它以*真、假、*或*汽车*为论据。默认值为*自动*。*可拖动*属性取决于浏览器。如果我们设置值*为真*，那么图像是可拖动的。如果我们设置值*为假，*图像不可拖动。

**语法:**

```html
<img src="" alt="" draggable="true">
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
  <body>
    <h2 style="color: green">GeeksforGeeks</h2>

    <p><b>Draggable image</b></p>

    <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210810224356/geeksimage2-200x146.png"
         alt="image" draggable="true"/>
  </body>
</html>
```

**输出:**

![](img/6b9a9a85c73c366338c55c52adf670d5.png)

可拖动图像