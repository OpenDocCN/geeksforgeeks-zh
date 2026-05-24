# 如何使用图像比较滑块比较两幅图像？

> 原文：[https://www.geeksforgeeks.org/how-to-compare-two-images-using-image-comparison-slider/](https://www.geeksforgeeks.org/how-to-compare-two-images-using-image-comparison-slider/)

在这个项目中，我们将创建一个图像滑块，我们可以用它来检查 2 个图像。如果我们要复制它们。我们可以在垂直和水平方向上比较第一幅图像和第二幅图像的每个边界。

## 方法：

*   创建一个 HTML 文件，在其中添加主 `div`，此外，我们将添加两个 `div` 来添加图像。
*   创建一个 CSS 文件并将图像添加到各自的 `div` 中。
*   创建一个 JavaScript 文件来改变方向并比较两张图片。

### HTML 代码：

*   首先，创建一个 HTML 文件（`index.html`）。
*   现在，HTML 文件创建后，我们将使用标签为网页提供标题。它应放在标签之间。
*   然后我们链接提供所有背景图片的 CSS 文件到我们的 HTML。这也放在标签上。
*   来到我们 HTML 代码的主体部分。
    *   首先，创建一个主 div 作为主框。
    *   在 `div` 中，添加两个 `div` 以增加图像 1 和图像 2。
    *   在主体末尾添加标签，该标签将 JavaScript 文件与我们的 HTML 文件链接起来。

## index.html

```html
<!DOCTYPE html>
<html lang="en">
<head>    
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>
      PRESS:'v' for vertical movement & 'h' \
      for horizontal movement
    </h1>
    <div class="main_box">
        <div class="img1"></div>
        <div class="img2"></div>
    </div>
    <script src="index.js"></script>
</body>
</html>
```