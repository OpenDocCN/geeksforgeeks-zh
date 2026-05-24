# HTML `<base>`标签

> 原文:[https://www.geeksforgeeks.org/html-base-tag/](https://www.geeksforgeeks.org/html-base-tag/)

HTML 基本标记用于为相对链接指定一个基本 URI 或网址。该网址将是页面上每个链接的基本网址，并将在每个链接之前加上前缀。例如，如果+
基本标记指定的 URL 是“www.xyz.com”，那么页面上的每隔一个 URL 都将以“www.xyz.com/”作为前缀。

**要点**:

*   基础标签必须定义在头部标签之间。
*   一个页面中最多只能有一个基本标签。

**语法:** :

```html
<base href = "SAMPLE_URL">
```

**示例:**请注意，我们只为图像指定了一个相对地址。由于我们已经在标题部分指定了一个基本 URL，浏览器将在“https://media . geeksforgeeks . org/WP-content/uploads/1-95 . jpg”中查找该图像。也就是说，在下面的程序中，我们已经为所有链接指定了一个基本 URL“https://media . geesforgeks . org/WP-content/uploads/”，当我们在 URL“1-95 . jpg”处引用图像时，浏览器实际上是从“https://media . geesforgeks . org/WP-content/uploads/1-95 . jpg”呈现图像。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
  <head>
    <!-- Declaring the BASE URL -->
    <base
      href="https://media.geeksforgeeks.org/wp-content/uploads/"
      target="_blank"
    />
  </head>

  <body>
    <img src="1-95.jpg" width="400" height="250" />
  </body>
</html>
```

**输出:**

![](img/e65fe7b3e565df0745abe57236b4ea35.png)

**支持的浏览器:**

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队