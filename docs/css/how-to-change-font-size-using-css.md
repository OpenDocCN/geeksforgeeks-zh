# 如何使用 CSS 改变字体大小？

> 原文:[https://www . geesforgeks . org/how-change-font-size-use-CSS/](https://www.geeksforgeeks.org/how-to-change-font-size-using-css/)

本文的目的是使用 CSS 改变[字号](https://www.geeksforgeeks.org/css-font-size-property/)。

**字体大小** CSS 属性设置字体的大小。有多种方式指定字体大小，包括*像素*或 *ems* 的关键字或数值。根据特定网页的需要选择合适的方法。

**语法:**

```html
font-size: medium|xx-small|x-small|small|large|x-large
|xx-large|smaller|larger|length|initial|inherit;
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      .div1 {
        font-size: 1.2em;
      }
      .div2 {
        font-size: smaller;
      }
      .div3 {
        font-size: 80%;
      }
      .div4 {
        font-size: 12px;
      }
      .div5 {
        font-size: x-small;
      }
    </style>
  </head>
  <body>
    <div class="div1">GeeksforGeeks</div>
    <div class="div2">GeeksforGeeks</div>
    <div class="div3">GeeksforGeeks</div>
    <div class="div4">GeeksforGeeks</div>
    <div class="div5">GeeksforGeeks</div>
  </body>
</html>
```

**输出:**

![](img/454d8027657ec15c9757cffee1e7356a.png)

不同的字体大小