# HTML | iframe 滚动属性

> 原文:[https://www . geesforgeks . org/html-iframe-scrolling-attribute/](https://www.geeksforgeeks.org/html-iframe-scrolling-attribute/)

**HTML < iframe >滚动属性**用于指定滚动条是否显示在< Iframe >元素中。基本上，当内容比 Iframe 元素大时，使用滚动条。

**语法**

```html
<iframe scrolling="auto | yes | no">
```

**属性值**

*   **自动:**有默认值。需要时会出现滚动条。
*   **是:**该值显示 Iframe 元素中的滚动条。
*   **否:**该值不显示 Iframe 元素中的滚动条。

**示例:**

```html
<!DOCTYPE html>
<html>

<body>
    <h1>
    GeeksForGeeks
    </h1>
    <h2>
        HTML Iframe scrolling Attribute
    </h2>

    <p>Content goes here</p>

    <iframe src="https://ide.geeksforgeeks.org/tryit.php" 
            height="300" 
            width="400" 
            marginwidth="50" 
            scrolling="no">
    </iframe>

</body>

</html>
```

**输出:**
![](img/b96d9e8d016ef4b6436154fe40c18fea.png)

**支持的浏览器:**以下列出了 **HTML < iframe >滚动属性**支持的浏览器:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧