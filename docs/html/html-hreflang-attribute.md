# HTML | hreflang 属性

> 原文:[https://www.geeksforgeeks.org/html-hreflang-attribute/](https://www.geeksforgeeks.org/html-hreflang-attribute/)

**HTML hreflanging 属性**用于指定链接文档的语言。它仅在设置了 href 属性时使用。
**语法:**

```html
<element hreflang="language_code"> 
```

**适用**

*   [<一>](https://www.geeksforgeeks.org/html-a-hreflang-attribute/?ref=rp)
*   [<地区>](https://www.geeksforgeeks.org/html-area-hreflang-attribute/?ref=rp)
*   [<链接>](https://www.geeksforgeeks.org/html-link-hreflang-attribute/?ref=rp)

**示例:**本示例说明了 hreflang 属性在锚点元素中的使用。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML hreflang Attribute
    </title>
</head>

<body>
    <center>
        <h1>
        GeeksForGeeks
    </h1>

        <h2>
        HTML <a> hreflang Attribute
    </h2>

<p>Welcome to
            <a href=
"http://www.example.com:4097/test.htm#part2"
            id="GFG"
            rel="nofollow"
            hreflang="en-us"
            target="_self">
                GeeksforGeeks
            </a>
        </p>

    </center>
</body>

</html>
```

**输出:**

![](img/6d9a7235248b7d331be42e240a719155.png)

**支持的浏览器:**属性*支持的浏览器如下:* 

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队