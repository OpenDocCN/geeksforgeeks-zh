# 使用 HTML & CSS

打开或关闭灯泡

> 原文:[https://www . geesforgeks . org/on-on-or-off-bulb-use-html-CSS/](https://www.geeksforgeeks.org/turn-on-or-off-bulb-using-html-css/)

HTML 框架用于将浏览器窗口分成多个部分，每个部分加载一个单独的 HTML 文档。在这个项目中，我们将制作一个网页，当用户点击时，它将打开和关闭一个灯泡。我们将使用 HTML 框架和框架集功能和一些 CSS 来设计我们的开和关按钮。

**进场:**

*   要使用框架，我们已经使用了 **[<框架集>](https://www.geeksforgeeks.org/html-frameset-tag/)** 标记代替了 **[<主体>](https://www.geeksforgeeks.org/html-body-tag/)** 标记。 **<框架集>** 标签定义了如何将窗口分成框架。 **<框架集>** 标签的 row 属性定义水平框架， **cols** 属性定义垂直框架。在框架内部，我们使用了 **src** 属性，该属性用于给出应该加载到框架中的文件名。
*   另外，我们创建了两个文件，即 ON.html 和 OFF.html，其中分别有灯泡处于打开和关闭位置的图像。每当用户按下 on 时，ON 文件被加载到框架中，每当按下 off 时，OFF 文件被加载。

**示例:**

## index.html

```html
<!DOCTYPE html>
<html lang="en">

<!--Setting the frames and opening 
on and off html-pages-->
<frameset cols="25%,75%">
    <frame src="main.html" name="left-frame"></frame>
    <frame src="off.html" name="right-frame"></frame>
</frameset>

</html>
```