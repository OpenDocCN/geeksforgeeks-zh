# HTML 5

## `<nav>` 和 `<menu>` 标签的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-nav-and-menu-tag-in-html5/](https://www.geeksforgeeks.org/difference-between-nav-and-menu-tag-in-html5/)

**`<nav>` 标签:**
`<nav>` 标签用于指定同一文档或任何其他文档内的导航链接，这意味着它提供指向同一或不同页面/文档上的内容的链接。

**示例:**

```html
<!DOCTYPE html>
<html>

<body>
    <h1>The nav element</h1>
    <p>The nav element defines navigation links:</p>
    <nav>
        <a href="/home/">HOME</a> |
        <a href="/category/">CATEGORY</a> |
        <a href="/profile/">PROFILE</a> |
    </nav>
</body>

</html>
```

**输出:**
![](img/b7a03151c967f0f2352f2ff8da947545.png)

**示例:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>nav tag</title>
    <style>
        nav {
            border:2px;
            background-color:#090;
            color:white;
            padding:8px;
        }
        a {
            color:white;
            font-size:25px;
        }
        .gfg {
            font-size:30px;
            color:#090;
            font-weight:bold;
            text-align:center;
        }
        .nav_tag {
            text-align:center;
        }
    </style>
</head>
<body>
    <div class = "gfg">GFG</div>
    <div class = "nav_tag">Nav Element Example</div>
    <nav>
        <a href = "https://www.geeksforgeeks.org/">Home</a> |
        <a href = "https://www.geeksforgeeks.org/category/difference-between/">Difference Between</a> |
        <a href = "https://www.geeksforgeeks.org/company-interview-corner/">Interview</a> |
        <a href = "https://practice.geeksforgeeks.org/courses/">Courses</a> |
    </nav>
</body>
</html>
```

**输出:**
![](img/da40ed11b0656a934796c8d60bb5383d.png)

**`<menu>` 标签:**
HTML 中的 `<menu>` 标签用于创建菜单列表。它定义了用户可以用来创建列表表单控件、工具栏、上下文菜单和命令的命令列表。`<menu>` 标签从 HTML 中移除，并在 HTML5 中重新引入。大多数平台都不支持它。

`<menu>` 标签的内容: