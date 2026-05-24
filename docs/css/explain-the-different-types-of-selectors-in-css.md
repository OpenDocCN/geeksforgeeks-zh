# 解释 CSS 中选择器的不同类型

> 原文:[https://www . geeksforgeeks . org/解释不同类型的 css 选择器/](https://www.geeksforgeeks.org/explain-the-different-types-of-selectors-in-css/)

一个 [**CSS 选择器**](https://www.geeksforgeeks.org/css-syntax-and-selectors/) 选择 HTML 元素进行样式化。CSS 选择器根据其 id、类、类型、属性等选择 HTML 元素。

有许多基本的不同类型的选择器。

*   Element selector
*   Id selector
*   Class selector
*   Universal selector
*   Group selector

**HTML 代码:**考虑示例代码，以便更好地理解选择器及其用途。

## HTML

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href="style.css">
</head>

<body>
    <h1>
        Sample Heading
    </h1>

    <p>
        Geeks for Geeks is a computer science 
        portal for geeks and computer enthusiasts.
        Geeks for geeks provide a variety of 
        services for you to learn, thrive and
        also, have fun! Free Tutorials, Millions 
        of Articles, Live, Online and Classroom 
        Courses, Frequent Coding Competitions,
        Webinars by Industry Experts, Internship 
        opportunities and Job Opportunities.
    </p>

    <div id="div-container">
        Geeks for geeks is a computer science 
        portal for geeks and computer enthusiast.
        Geeks for geeks provide a variety of 
        services for you to learn, thrive and
        also, have fun! Free Tutorials, Millions 
        of Articles, Live, Online and Classroom 
        Courses, Frequent Coding Competitions,
        Webinars by Industry Experts, Internship 
        opportunities and Job Opportunities.
    </div>

    <p class="paragraph-class">
        Geeks for geeks is a computer science 
        portal for geeks and computer enthusiast.
        Geeks for geeks provide a variety of 
        services for you to learn, thrive and
        also, have fun! Free Tutorials, Millions 
        of Articles, Live, Online and Classroom 
        Courses, Frequent Coding Competitions,
        Webinars by Industry Experts, Internship 
        opportunities and Job Opportunities.
    </p>
</body>

</html>
```