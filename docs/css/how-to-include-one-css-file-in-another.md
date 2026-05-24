# 如何将一个 CSS 文件包含在另一个 CSS 文件中？

> 原文:[https://www . geesforgeks . org/how-to-include-one-CSS-file-in-other/](https://www.geeksforgeeks.org/how-to-include-one-css-file-in-another/)

**一个 CSS 文件可以包含在另一个 CSS 文件中吗？**
是的，可以把一个 CSS 文件包含在另一个 CSS 文件中，并且可以做多次。另外，在主 HTML 文件或主 CSS 文件中导入多个 CSS 文件。这可以通过使用@import 关键字来完成。

**例 1:**

*   **HTML 版块:**文件名为**index.html**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
    <head>
    <!-- linking css file with html file -->
    <link rel="stylesheet" href="style1.css">
    </head>

    <body>
        <center>
        <marquee><h1>GeeksforGeeks</h1> </marquee>
        <div class="css1">GeeksforGeeks: It is a computer science
        portal. It is an educational website. Prepare for the
        Recruitment drive of product based companies like
        Microsoft, Amazon, Adobe etc with a free online placement
        preparation course.
        </div>
        </center>
    </body>
</html>                               
```

*   **输出:**不使用 CSS 文件

![](img/5ea548b598125e968a67ed427bf282f8.png)

*   **CSS 第 1 节:**文件名为 **style1.css**

## 半铸钢ˌ钢性铸铁(Cast Semi-Steel)

```html
<!-- Including one css file into other -->
@import "style2.css";

 h1 {
     color:green;  
 }

.css1 {
     color:black;
     background-image: linear-gradient(to right, #DFF1DF, #11A00C);
     position:static;  
 }
```