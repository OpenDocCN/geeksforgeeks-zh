# HTML |源 src 属性

> 原文:[https://www.geeksforgeeks.org/html-source-src-attribute/](https://www.geeksforgeeks.org/html-source-src-attribute/)

**HTML <来源> src 属性**用于指定媒体资源的 URL。源元素用作<音频>和<视频>元素的子元素。

**语法:**

```html
<source src="URL">
```

**属性值:**包含指定媒体资源网址的单值网址。下面列出了两种类型的网址链接:

*   **绝对 URL:** 指向另一个网页。
*   **相对 URL:** 指向同一网页的其他文件。

下面的例子说明了 HTML 中的<source> src 属性:

**示例:**

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title>
        HTML source src Attribute
    </title>
</head> 

<body style="text-align:center;">

    <h1 style="color:green;">
        GeeksforGeeks
    </h1> 

    <h2>HTML Source src Attribute</h2> 

    <audio controls> 
        <source id="mySource" src="gameover.wav"
                type="audio/mpeg"> 

        <source src="gameover.ogg" type="audio/ogg"> 
    </audio> 
</body> 

</html>                    
```

**输出:**
![](img/c6781767c91bc13373280eb6beb11477.png)

**支持的浏览器:**HTML<源码> src 属性支持的浏览器如下:

*   谷歌 Chrome 4.0
*   Internet Explorer 9.0
*   Firefox 3.5
*   Safari 4.0
*   歌剧 10.5