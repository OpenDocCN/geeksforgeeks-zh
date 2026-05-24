# Tailwind CSS 垂直对齐

> 原文：[https://www.geeksforgeeks.org/tailwind-css-vertical-alignment/](https://www.geeksforgeeks.org/tailwind-css-vertical-alignment/)

该类在 [Tailwind CSS](https://www.geeksforgeeks.org/css-tailwind-introduction/) 中接受多个值。所有的属性都包含在类的形式中。它是 [CSS 垂直对齐属性](https://www.geeksforgeeks.org/css-vertical-align-property/)的替代品。此类用于指定表格框或内联元素的垂直对齐方式。

## 垂直校准等级

*   `align-baseline`：它将元素基线与父元素的基线相对应对齐。这可能因浏览器而异。这是默认值。
*   `align-top`：将元素的顶部与其线上最高元素的顶部对齐。
*   `align-middle`：将元素的中间与父元素的中间对齐。
*   `align-bottom`：将元素的底部与其线上最短元素的顶部对齐。
*   `align-text-top`：它将元素顶部与父字体的顶部相对应对齐。
*   `align-text-bottom`：将元素的底部与父字体的底部对齐。

## 语法

```html
<element class="align-{Vertical Alignment}">...</element>
```

## 示例

### HTML

```html
<!DOCTYPE html> 
<html>
<head> 
    <link href="https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css" rel="stylesheet"> 
</head>

<body class="text-center mx-4 space-y-2"> 
    <h1 class="text-green-600 text-5xl font-bold">
        GeeksforGeeks
    </h1> 
    <b>Tailwind CSS Text Overflow Class</b> 
    <div class="mx-4 h-24 rounded-lg grid grid-cols-2 text-left ">

<p>
        <img src="https://media.geeksforgeeks.org/wp-content/uploads/gfgc.png" class="inline-block align-baseline">
             align-baseline
      </p>

<p>
        <img src="https://media.geeksforgeeks.org/wp-content/uploads/gfgc.png" class="inline-block align-top">
             align-top
      </p>

<p>
        <img src="https://media.geeksforgeeks.org/wp-content/uploads/gfgc.png" class="inline-block align-middle">
             align-middle
      </p>

<p>
        <img src="https://media.geeksforgeeks.org/wp-content/uploads/gfgc.png" class="inline-block align-bottom">
             align-bottom
      </p>

<p>
        <img src="https://media.geeksforgeeks.org/wp-content/uploads/gfgc.png" class="inline-block align-text-top">
             align-text-top
      </p>

<p>
        <img src="https://media.geeksforgeeks.org/wp-content/uploads/gfgc.png" class="inline-block align-text-bottom">
             align-text-bottom
      </p>

</div>
</body>

</html> 
```

## 输出

![](img/fd518d1c204a83ed10aa4098be9e1ad6.png)