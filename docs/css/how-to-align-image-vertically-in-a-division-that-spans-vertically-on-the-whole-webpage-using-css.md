# 如何使用 CSS 在整个网页上垂直跨越的分区中垂直对齐图像？

> 原文:[https://www . geeksforgeeks . org/如何使用-css/](https://www.geeksforgeeks.org/how-to-align-image-vertically-in-a-division-that-spans-vertically-on-the-whole-webpage-using-css/) 垂直对齐跨整个网页的垂直分割图像

在本文中，我们将讨论在垂直横跨整个网页的单个分区中图像的垂直对齐。图像的垂直对齐是指将图像放置在一列中。我们经常需要垂直对齐图像，以便在移动版本上正确显示，或者有时，我们不想插入水平滚动条。为此，我们将使用 CSS flex 属性。

**进场:**

*   创建一个 div 标签来放置图像。
*   在标签中，使用 s *rc* 属性提供图像路径，使用 *alt* 属性提供替代文本。
*   添加 CSS 属性以垂直对齐方式显示图像。

**示例 1:** 在本例中，我们使用了文本来说明图像与文本的垂直对齐。为此，我们使用了*垂直对齐* CSS 属性将其垂直对齐。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Vertical images layout</title>
    <style>
      body {
        background: rgb(225, 227, 222);
      }
      .container {
        border: 1px solid black;
        height: 205px;
        width: 590px;
        padding: 5px;
        margin-top: 180px;
        margin-left: 350px;
        border-radius: 5px;
      }
      .container img {
        width: 200px;
        height: 200px;
        padding: 3px;
        border-radius: 7px;
      }
      span {
        padding: 1px;
        font-size: 60px;
        color: green;
        vertical-align: 128%;
      }
    </style>
  </head>

  <body>
    <div class="container">
      <img src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png"
        alt="image-2"/>
      <span>GeeksforGeeks</span>
    </div>
  </body>
</html>
```

**输出:**从输出中，我们可以看到与文本垂直对齐的图像。

![](img/81a7ac909f13d8744eac55d44724de19.png)

为了垂直对齐系列图像，我们将使用 CSS 显示属性结合*对齐-项目* & *伸缩-方向*属性。我们需要创建一个父元素。使用*将父元素声明为 flexbox 后显示:flex，*我们可以使用*对齐-项目:中心，将项目对齐到中心；*使用*将柱的方向设置为垂直-方向:柱；。*

**语法:**

```html
.class_name {
    display: flex;
    flex-direction: column;
    align-items: center;
}
```

我们将在[样式](https://www.geeksforgeeks.org/html-style-tag/)标签中声明 CSS 属性来改变布局。

1.  **显示:**[**flex**](https://www.geeksforgeeks.org/css-flex-property/)**–**CSS 中的 flex 属性分别用于设置柔性项的长度和扩展或收缩项以填充多余空间或防止溢出。
2.  [](CSS | flex-direction Property)****:列–**此属性用于垂直对齐应用它的类的项目。**
3.  **[**对齐-项目**](https://www.geeksforgeeks.org/css-align-items-property/) **:居中–**该属性用于显示屏幕中央的项目。**

****示例 2:** 在本例中，我们将使用上述方法垂直显示图像。**

## **超文本标记语言**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Vertical images layout</title>
    <style>
      body {
        background: rgb(225, 227, 222);
      }
      .container {
        display: flex;
        flex-direction: column;
        align-items: center;
      }
      .container img {
        width: 200px;
        height: 200px;
        padding: 3px;
        margin-left: 3px;
      }
    </style>
  </head>

  <body>
    <div class="container">
      <img src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/gfg_200x200-min.png"
        alt="image-1"/>
      <img src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png"
        alt="image-2"/>
      <img src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/gfg_200x200-min.png"
        alt="image-3"/>
    </div>
  </body>
</html>
```

****输出:**在这里，我们可以看到 3 张图像都是垂直对齐的。**

**![](img/b66c2725f35f67cc9f51b2e24a4f92d3.png)**

****注**:如果不需要明确定义图片的大小，图片会覆盖整个网页。图像的大小可以根据需要而变化。**

****支持的浏览器:****

*   **谷歌 Chrome 29.0**
*   **Firefox 28.0**
*   **微软边缘 11.0**
*   **Safari 9.0**
*   **Opera 17.0**