# HTML 5 `<summary>` 标签

> 原文：[https://www.geeksforgeeks.org/html-5-summary-tag/](https://www.geeksforgeeks.org/html-5-summary-tag/)

HTML 中的 `<summary>` 标签用于定义 `<details>` 元素的概要。

*   `<summary>` 元素与 `<details>` 元素一起使用，并提供用户可见的摘要。
*   当用户点击摘要时，放置在 `<details>` 元素内的内容变得可见，而之前是隐藏的。
*   在 HTML 5 中添加了 `<summary>` 标签。
*   `<summary>` 标记需要开始和结束标记。

**语法：**

```html
<summary> Content </summary>
```

下面程序说明了 `<summary>` 元素：

## 示例

```html
<!DOCTYPE html>
<html>
<body>

<details>
  <!-- html summary tag is used here -->
  <summary>GeeksforGeeks.</summary>

<p> It is a portal for geeks.</p>

</details>

</body>
</html>
```

**输出：**

[https://media.geeksforgeeks.org/wp-content/uploads/summary-tag-1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/summary-tag-1.mp4)

**支持的浏览器：**

*   谷歌 Chrome 12.0
*   Firefox 48.0
*   Opera 15.0
*   Safari 6.0