# 如何在 HTML 中移动图像？

> 原文:[https://www.geeksforgeeks.org/how-to-move-image-in-html/](https://www.geeksforgeeks.org/how-to-move-image-in-html/)

您可以使用 [**<【字幕】>**](https://www.geeksforgeeks.org/html-marquee-tag/) 标签轻松移动 HTML 中的图像。它用于创建从水平方向从左到右或从右到左，或从垂直方向从上到下或从下到上的滚动图像。默认情况下，在 *<字幕>* 标签内找到的图像将从右向左滚动。

**语法:**

```html
<marquee>
   <img src="">
</marquee>
```

**T2 选框>标签的属性:**

*   **方向**:设置滚动图像的方向。该属性的值可以是*左、右、上*或*下*。
*   **行为:**行为讲述了文本如何滚动。它可以是以下值之一，即*交替、滚动、滑动。*

**示例 1:** 以下示例使用*滚动*行为。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
<center>
    <!-- The image has scrolling behavior to left -->
    <marquee  behavior="scroll" direction="left">        
          <img src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png"
          alt="GeeksforGeeks logo"> 
    </marquee>  

   <!-- The image has scrolling behavior to the upper direction. -->
   <marquee  behavior="scroll" direction="up">         
          <img src= 
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png"
          alt="GeeksforGeeks logo"> 
    </marquee>  
</center>
</body>
</html>
```

**输出:**

![](img/47938ad0575d56c2afa197ca12fab81c.png)

**示例 2:** 以下示例使用了*替代* **的**行为。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<body>

<center>
    <marquee  behavior="alternate" direction="left">          
          <img src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png"
          alt="GeeksforGeeks logo"> 
    </marquee>  

   <marquee  behavior="alternate" direction="right">         
          <img src= 
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png"
          alt="GeeksforGeeks logo"> 
    </marquee>  
</center>

</body>
</html>
```

**输出:**

![](img/9d10d3312479a3dda2b8d0b8586e9845.png)