# HTML | DOM 引用属性

> 原文:[https://www.geeksforgeeks.org/html-dom-referrer-property/](https://www.geeksforgeeks.org/html-dom-referrer-property/)

HTML 中的 **DOM referrer 属性**用于返回链接到当前页面的页面的 URI。如果用户直接或通过书签导航到页面，则该值为空字符串。
**语法:**

```html
document.referrer
```

**返回值:**一个字符串，表示加载当前文档的文档的网址。返回整个网址，包括协议(如 http://)。如果当前文档不是通过链接(例如，通过书签)打开的，则返回一个空字符串。

下面的程序说明了 HTML 中的 referrer 属性:
**示例:**有 3 个页面相互链接，并在下面指定它们的 referrer 属性。

page1.html

第 2 页. html

第 3 页. html