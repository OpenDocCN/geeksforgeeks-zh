# HTML |脚本 src 属性

> 原文:[https://www.geeksforgeeks.org/html-script-src-attribute/](https://www.geeksforgeeks.org/html-script-src-attribute/)

**HTML <脚本> src 属性**用于指定外部 JavaScript 文件的 URL。外部 JavaScript 文件用于在网站的几个页面上运行相同的脚本。我们可以保存扩展名为. js 的 JavaScript 文件。我们可以使用<脚本>元素的 src 属性引用外部脚本。

**语法:**

```html
<script src="URL">
```

**属性值:**包含单值 URL，指定外部 JavaScript 文件的 URL。下面列出了两种类型的网址链接:

*   **绝对 URL:** 指向另一个网页。
*   **相对 URL:** 指向同一网页的其他文件。

下面的例子说明了 HTML 中的 

**示例:**

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
    HTML  script src Attribute 
    </title> 
</head> 

<body style="text-align:center;"> 
    <h1> 
        GeeksForGeeks 
    </h1> 

    <h2> 
        HTML script src Attribute
    </h2> 

    <script id="myGeeks"
            type="text/javascript"
            src="my_script.js"> 
    </script> 
    <br> 
    <button>Submit</button>

</body> 

</html> 
```

**输出:**
![](img/7a6e7ee601bb9ef2d462992812f299ae.png)

**支持的浏览器:**HTML<脚本> src 属性支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧