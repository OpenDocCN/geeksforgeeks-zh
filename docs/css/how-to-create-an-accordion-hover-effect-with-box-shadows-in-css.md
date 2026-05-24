# 如何在 CSS 中创建带有框阴影的手风琴悬停效果？

> 原文:[https://www . geeksforgeeks . org/如何创建带有 css 中阴影的手风琴悬停效果/](https://www.geeksforgeeks.org/how-to-create-an-accordion-hover-effect-with-box-shadows-in-css/)

本文的目的是使用框阴影来创建手风琴悬停效果。

**方法:**[CSS 框阴影](https://www.geeksforgeeks.org/css-box-shadow-property/)属性用于在元素周围绘制阴影。 [CSS 框影](https://www.geeksforgeeks.org/css-box-shadow-property/)属性有以下语法。

**语法:**

```html
box-shadow : x-offset y-offset blur-radius spread-redius color
```

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
   <body style="text-align: center;">
      <style>
         .info {
         position: relative;
         max-width: 100%;
         font-size: 60px;
         }
         .info label, .info-content {
         padding: 10px;
         display: block;
         }
         .info label {
         background: #808080;
         }
         .info-content {
         background: #ffffff;
         display: none;
         }
         .info input {
         display: none;
         }
         .info input:checked ~ .info-content {
         display: block;
         border:solid;
         }
         .info label:hover {
         box-shadow: inset 0 0 10px red;            
         }
      </style>
      <div class="info">
         Hover mouse over this accordion to see box-shadow 
         in action. After that click on accordion to show
         its content.
         <input id="info1" type="checkbox" />
         <label for="info1">Geeks For Geeks</label>
         <div class="info-content">
            A Computer Science portal for geeks. It contains 
            well written, well thought and well explained 
            computer science and 
            programming articles, quizzes
            and videos.
         </div>
      </div>
   </body>
</html>
```

**输出:**你可以看到悬停效果的红色阴影。

*   **点击前:**我们看到如下网页。
    T3】
*   **点击后:**你会看到“GeeksForGeeks”手风琴的内容。
    T3】