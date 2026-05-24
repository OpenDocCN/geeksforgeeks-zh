# 如何设置 CSS 中不同元素的文字颜色？

> 原文:[https://www . geesforgeks . org/如何设置 css 中不同元素的文本颜色/](https://www.geeksforgeeks.org/how-to-set-the-text-color-for-different-elements-in-css/)

颜色对于给网站一个好的外观和吸引用户非常重要。因此，添加了不同颜色的文本元素来增强网页的视觉效果。 [CSS 颜色属性](https://www.geeksforgeeks.org/css-color-property/)定义了一个 HTML 元素的文本颜色。

要为 CSS 中的不同元素设置[文本颜色](https://www.geeksforgeeks.org/css-text-formatting/)，请添加适当的 CSS 选择器，并用所需的颜色值定义[颜色](https://www.geeksforgeeks.org/css-color-property/)属性。

**语法:**

```html
color:value;
```

**注意:**在 CSS 中有不同的方式来指定颜色值，例如使用颜色关键字、RGB 颜色值、十六进制颜色值等等。

**示例:**在以下示例中，标题为*绿色*颜色，如< h3 >样式标记中所指定的，“内容”类具有*灰色*颜色文本，而普通 *< p >* 标记中的文本具有*黑色*文本颜色，这是正文选择器中定义的页面的默认*文本颜色*。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      body {
        text-align: center;
        font-size: 15px;
        color: black;
      }

      h3 {
        text-align: center;
        font-size: 60px;
        color: green;
      }

      p.content {
        color: grey;
      }
    </style>
  </head>
  <body>
    <h3>GeeksforGeeks</h3>

    <p>A Computer Science portal for geeks</p>

    <p class="content">
      It is a one-stop destination for all 
      Computer Science students!! It is a
      platform that fulfill all their needs 
      such as- Tutorials & Courses,
      Placement preparation, Interview 
      Experiences, and various others.
    </p>
  </body>
</html>
```

**输出:**

![](img/f87998e822216a05834c610387ec2fbb.png)

不同元素的文本颜色