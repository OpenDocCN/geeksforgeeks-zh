# CSS |出血属性

> 原文:[https://www.geeksforgeeks.org/css-bleed-property/](https://www.geeksforgeeks.org/css-bleed-property/)

**CSS 出血属性**用于将页面出血区域扩展到内容框之外。该属性裁剪了其周围的所有内容，并将其放入框中。该属性是目前处于开发模式的页面媒体的一部分。CSS 出血属性在 [@page](https://www.geeksforgeeks.org/css-page-rule/) 规则下更有意义。当你想打印任何扩展到页面边缘的内容时，这个属性是有帮助的。很少有打印机不允许打印页面边缘。使用出血**属性**允许区域可打印。所以当页面被修剪掉的时候，内容最终会被删除。

**语法:**

```html
bleed: auto | length;
```

**属性:**

*   **auto:** 它的默认值为零，除非用户创建一个 marks 属性，使默认值为 6pt。
*   **长度**它保存一个数字，表示内容将延伸出盒子的多少。

下面的例子说明了 **CSS 出血属性。**
**例:**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>CSS bleed property</title>
    <style type="text/css">
        /* default for all pages */

        @page {
            margin: 2in;
        }
        /* margin on left page */

        @page :left {
            margin: 1in;
            bleed: 10pt;
        }
        /* margin on right page */

        @page :right {
            margin: 3in;
            bleed: 10pt;
        }
        /* top margin on first page */

        @page :first {
            margin-top: 5in;
        }

        h1 {
            color: green;
        }
    </style>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>
        <h2>CSS bleed property</h2>
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190821162842/colorMatrixImage1.png" 
             alt="" />
    </center>

</body>

</html>
```

**输出:**geeks forgeeks 图像的较暗部分是内容的出血区域。
T3】

**支持的浏览器:**主要浏览器不支持 **CSS 出血属性。**