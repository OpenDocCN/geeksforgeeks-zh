# HTML | a rel 属性

> 原文:[https://www.geeksforgeeks.org/html-a-rel-attribute/](https://www.geeksforgeeks.org/html-a-rel-attribute/)

**rel 属性**用于指定当前文档和链接文档之间的关系。它仅在 href 属性存在时使用。

**语法:**

```html
<a rel="value">
```

**属性值:**

*   **替代版本:**它定义了文档的替代版本，即打印页面、翻译版本或镜像版本。
*   **作者:**定义文档的作者。
*   **书签:**指定相关文档。
*   **帮助:**指定帮助文档。
*   **许可:**定义文档的版权信息。
*   **下一步:**定义选择中的下一个文档。
*   **nofollow:** 它被谷歌使用，用来指定谷歌搜索蜘蛛不应该跟随那个链接，并且主要用于付费链接。
*   **noreferrer:** 用于指定如果用户跟随超链接，浏览器不应发送 HTTP referer 头。
*   **预取:**指定缓存目标文档。
*   **prev:** 指定选择中的上一个文档。
*   **搜索:**指定文档的搜索工具。
*   **标签:**指定当前文档的标签关键字。

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>HTML a rel Attribute</title>
</head>

<body>
    <p>Welcome to
        <a rel="noopener" 
           href="https://ide.geeksforgeeks.org/"> 
                GeeksforGeeks 
            </a>
    </p>
</body>

</html>
```

**输出:**
![](img/a2bff5c3dd28b1802ec5776db50c3b4f.png)

**支持的浏览器:**以下列出了 *HTML < a > rel 属性*支持的浏览器:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧