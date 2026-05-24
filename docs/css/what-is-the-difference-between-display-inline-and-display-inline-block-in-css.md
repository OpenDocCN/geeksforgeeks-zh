# CSS 中的 display: inline 和 display: inline-block 有什么区别？

> 原文:[https://www . geesforgeks . org/display-inline 和 display-inline-block-in-css 之间的区别是什么/](https://www.geeksforgeeks.org/what-is-the-difference-between-display-inline-and-display-inline-block-in-css/)

CSS 中的 display 属性是一个非常有用且常用的属性，它包含很多值。本文包含*显示:内联*和*显示:内联-阻止*属性。

**“显示:内联”属性:**该属性用于将元素显示为内联元素(如< span >)。高度和宽度属性在显示时不受影响:内嵌；财产。它只允许左边界和右边界，不允许上边界和下边界。简单地说，它的相邻元素前后都没有换行符，并且允许它旁边有 HTML。

**语法:**

```html
element {
    display: inline;
    // CSS property
}

```

**例 1:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>display:inline; property</title>
        <style>
            p {
                color: green;
            }
            .gfg {
                display: inline;
                padding: 15px 15px;
                border: 1px solid black;
                color:white;
                background-color:green;
            }
            div {
                text-align:justify;
            }
            h1 {
                color:green;
            }
            h1, h2 {
                text-align:center;
            }
        </style>
    </head>
    <body>
        <h1>GeeksforGeeks</h1>
        <h2>display: inline; property</h2>
        <div>Prepare for the Recruitment drive of product based
        companies like <span class = "gfg">Microsoft, Amazon, 
        Adobe</span> etc with a free online placement preparation
        course. The course focuses on various MCQ's & Coding question 
        likely to be asked in the interviews & make your upcoming 
        placement season efficient and successful.
        </div>
    </body>
</html>                    
```

**输出:**
![inline](img/216d3914c0ea1f78842a2f6ea6c66ded.png)

**“显示:内联块”属性:**该属性用于将元素显示为内联级块容器。元素本身被格式化为内嵌元素，但是它可以应用高度和宽度值。它作为内联元素放置(与相邻内容在同一行)。它看起来像一个内联元素，但它的行为就像一个块元素，不会强制换行。

**语法:**

```html
element {
    display: inline-block;
    // CSS property
}

```

**例 2:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>display:inline-block; property</title>
        <style>
            p {
                color: green;
            }
            .gfg {
                display: inline-block;
                padding: 15px 15px;
                border: 1px solid black;
                color:white;
                background-color:green;
            }
            div {
                text-align:justify;
            }
            h1 {
                color:green;
            }
            h1, h2 {
                text-align:center;
            }
        </style>
    </head>
    <body>
        <h1>GeeksforGeeks</h1>
        <h2>display: inline-block; property</h2>
        <div>Prepare for the Recruitment drive of product based
        companies like <span class = "gfg">Microsoft, Amazon, 
        Adobe</span> etc with a free online placement preparation
        course. The course focuses on various MCQ's & Coding question 
        likely to be asked in the interviews & make your upcoming 
        placement season efficient and successful.
        </div>
    </body>
</html>                    
```

**输出:**
![inline-block](img/e39314a5c22d90812b72888d00621624.png)