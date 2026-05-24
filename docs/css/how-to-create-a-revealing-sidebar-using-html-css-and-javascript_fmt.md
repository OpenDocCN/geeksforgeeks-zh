# 如何使用 HTML、CSS 和 JavaScript 创建一个揭示性的侧边栏？

> 原文: [https://www.geeksforgeeks.org/how-to-create-a-revealing-sidebar-using-html-css-and-javascript/](https://www.geeksforgeeks.org/how-to-create-a-revealing-sidebar-using-html-css-and-javascript/)

在本文中，我们将使用简单的 HTML CSS 和 JavaScript 创建一个旋转导航栏。当点击菜单按钮时，页面内容会旋转，导航栏会显示出来。

**方法:**

*   创建一个 HTML 文件，用于构建标题和导航栏。
*   创建 CSS 样式，为网页元素添加动画效果。
*   创建 JS 文件，添加能够检测鼠标点击事件的事件监听器。

## HTML 部分

在本部分中，我们将按照以下步骤定义页面的结构:

*   我们将首先创建一个 HTML 文件。
*   然后，我们将链接为 HTML 提供样式的 CSS 文件。
*   在 `body` 部分，我们添加了两个用于关闭和打开导航栏的图标。
*   最后，我们添加两个标签，一个用于我们的 `index.js` 文件，另一个用于网页上使用的图标。

### index.html

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