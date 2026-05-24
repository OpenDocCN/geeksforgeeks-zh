# 如何使用 HTML、CSS 和 JavaScript 创建一个揭示性的侧边栏？

> 原文:[https://www . geesforgeks . org/如何使用 html-CSS-和-javascript/](https://www.geeksforgeeks.org/how-to-create-a-revealing-sidebar-using-html-css-and-javascript/) 创建一个揭示性的侧边栏

在本文中，我们将使用简单的 HTML CSS 和 JavaScript 创建一个旋转导航栏。当点击菜单按钮时，页面内容会旋转，导航栏会显示出来。

**方法:**

*   Create an HTML file in which we will make the title and navigation bar.
*   Create a CSS style to give some animation effects to webpage elements.
*   Create a JS file to add an event listener that can detect mouse click events.

**HTML 部分:**在本部分中，我们将按照以下步骤定义页面的结构:

*   We will first create an HTML file.
*   Then we will link the CSS file that provides the style to our HTML.
*   In the body part, we added two icons for closing and opening the navigation bar.
*   Finally, we add two tags, one for our *index.js* file, and the other for the icons we use on the webpage.

## index.html

```html
<html>
<head>
  <link rel="stylesheet" 
        href="style.css">
</head>
<body>
  <div class="main_box show-nav">
    <div class="circle-container">
      <div class="circle">
        <button class="open">
          <i class="fas fa-bars"></i>
        </button>
        <button class="close">
          <i class="fas fa-times"></i>
        </button>
      </div>
    </div>
    <div class="content">
      <h1 style="color: green;">
        GeeksforGeeks
      </h1>
      <small>Hello Geeks</small>
      <p>
        GeeksforGeeks is a good platform to 
        learn programming. It is an educational
        website. Prepare for the Recruitment drive
        of product based companies like Microsoft,
        Amazon, Adobe etc with a free
        online placement preparation course. The
        course focuses on various MCQ's and Coding
        question likely to be asked in the interviews
        and make your upcoming placement season 
        efficient and successful.
      </p>

      <p>
        Also, any geeks can help other geeks by
        writing articles on the GeeksforGeeks,
        publishing articles follow few steps 
        that are Articles that need little
        modification or improvement from reviewers
        are published first. To quickly get your
        articles reviewed, please refer existing
        articles, their formatting style, coding 
        style, and try to make you are close to
        them. In case you are a beginner, you 
        may refer Guidelines to write an Article.
      </p>

    </div>
  </div>
  <nav>
    <ul class="nav-links">
      <li>home</li>
      <li>about</li>
      <li>contact</li>
    </ul>
  </nav>
  <script src="https://kit.fontawesome.com/704ff50790.js"
          crossorigin="anonymous"></script>
  <script src="index.js"></script>
</body>
</html>
```