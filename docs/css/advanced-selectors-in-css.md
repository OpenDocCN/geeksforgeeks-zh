# CSS 中的高级选择器

> 原文:[https://www.geeksforgeeks.org/advanced-selectors-in-css/](https://www.geeksforgeeks.org/advanced-selectors-in-css/)

选择器用于选择属性中的 HTML 元素。下面给出了一些不同类型的选择器:

*   **相邻同级选择器:**选择所有与指定元素相邻的同级元素。如果第二个元素紧跟在第一个元素之后，它将选择第二个元素。
    **语法**:它选择紧跟在 h4 标签后面的 ul 标签。

## 超文本标记语言

```html
h4+ul{
    border: 4px solid red;
}           
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
   <head>
      <title>adjacent</title>
      <style type="text/css">
         ul+h4{
         border:4px solid red;
         }
      </style>
   </head>
   <body>
      <h1>GeeksForGeeks</h1>
      <ul>
         <li>Language</li>
         <li>Concept</li>
         <li>Knowledge</li>
      </ul>
      <h4>Coding</h4>
      <h2>Time</h2>
   </body>
</html>
```