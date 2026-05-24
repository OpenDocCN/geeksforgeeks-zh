# HTML | <link> rel 属性

> 原文:[https://www.geeksforgeeks.org/html-link-rel-attribute/](https://www.geeksforgeeks.org/html-link-rel-attribute/)

**HTML rel 属性**用于指定当前和链接文档之间的关系。它仅在 href 属性存在时使用。
**语法:**

```html
<link rel="value">
```

**属性值**

*   **替代:**指定文档的替代链接(即打印页面、翻译或镜像)。
*   **作者:**它定义链接的作者
*   **dns-预取:**它指定浏览器应该为目标资源的源抢先执行 DNS 解析
*   **帮助:**指定帮助文档的链接。示例:<链接 rel = " help " href = " help/">
*   **图标:**指定给定文档中的导入图标
*   **许可证:**它指定了文档版权信息的链接
*   **下一步:**提供下一个文档的串联链接
*   **平回:**指定平回发球的地址
*   **预连接:**它指定目标应该抢先连接到源资源
*   **预取:**指定缓存目标文档。
*   **预加载:**指定浏览器必须先取后缓存
*   **先决条件:**指定浏览器应该加载
*   **prev:** 指定选择中的上一个文档
*   **搜索:**指定文档的搜索工具。
*   **样式表:**它导入样式表

**超文本链接相关属性示例**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <link rel="stylesheet"
        type="text/css"
        href="index_screen.css">

    <link rel="stylesheet"
        type="text/css"
        href="index_print.css">
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>

<p><a href="https://ide.geeksforgeeks.org/tryit.php"
        target="_blank">
    Click here
    </a>
    </center>
</body>

</html>                   
```

**输出:**

![](img/326c6740383ab34dcbc273713c8b0a9c.png)

**支持的浏览器:****HTML rel 属性**支持的浏览器如下

*   谷歌 Chrome 4.0
*   Firefox 4.0
*   苹果 Safari 4.0
*   歌剧 10.5
*   互联网浏览器/边缘