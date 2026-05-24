# 如何使用 jQuery 从特定页面移除全局 CSS 文件？

> 原文:[https://www . geesforgeks . org/how-to-remove-global-CSS-file-from-special-page-use-jquery/](https://www.geeksforgeeks.org/how-to-remove-global-css-file-from-a-particular-page-using-jquery/)

本文描述了从页面中移除全局 CSS 文件的方法。它可以用于模板可能包含全局 CSS 文件，并且您需要删除该文件以使任何其他 CSS 文件生效的情况。我们将在下面的示例中看到这一点:

考虑带有两个 CSS 文件导入的 index.html 文件，带有一个*和第二个 ***页面的 id 为*的*和一个*******页面的* 。 ***global.css*** 是跨所有页面保留的文件， ***page.css*** 是特定页面的文件。****

**下面的代码是针对**index.html**文件的。为了演示，同时包含了 global.css 和 page.css 文件。**

 **## HTML

```html
<!DOCTYPE html>
<html>

<head>
    <!--  CSS  -->
    <link id="one" type="text/css" 
        rel="stylesheet" href="global.css" />

    <link id="two" type="text/css" 
        rel="stylesheet" href="page.css" />
</head>

<body>
    <h1>GeeksForGeeks</h1>
    <h2>Welcome to GeeksForGeeks</h2>

    <div id="para-one">
        <p>
            A Computer Science portal for geeks. 
            It contains well written, well 
            thought and well explained computer 
            science and programming articles, 
            quizzes and questions. A Computer 
            Science portal for geeks. It contains 
            well written, well thought and well 
            explained computer science and 
            programming articles, quizzes and 
            questions.
        </p>
    </div>

    <div id="para-two">
        <p>
            A Computer Science portal for geeks. 
            It contains well written, well 
            thought and well explained computer 
            science and programming articles, 
            quizzes and questions. A Computer 
            Science portal for geeks. It contains 
            well written, well thought and well 
            explained computer science and 
            programming articles, quizzes and 
            questions.
        </p>
    </div>
</body>

</html>
```**