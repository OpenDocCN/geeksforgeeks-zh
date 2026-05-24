# HTML | <input> src 属性

> 原文:[https://www.geeksforgeeks.org/html-input-src-attribute/](https://www.geeksforgeeks.org/html-input-src-attribute/)

**HTML <输入> src 属性**用于*指定要用作提交按钮的图像的网址*。该属性不与 **<一起使用，输入类型=【图像】>** 。

**语法:**

```html
<input src="URL">
```

**属性值:**包含一个单值 URL，指定源图像的链接。下面列出了两种类型的网址链接:

*   **绝对 URL:** 指向另一个网页。
*   **相对 URL:** 指向同一网页的其他文件。

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML Input src Attribute
    </title>
</head>

<body style="text-align:center;">

    <h1 style="color:green;"> 
            GeeksForGeeks 
        </h1>

    <h2>HTML Input src Attribute</h2>
    <form>
        <input id="myImage" 
               type="image" 
               src=
"https://media.geeksforgeeks.org/wp-content/uploads/gfg-40.png" 
               alt="Submit"
               width="70"
               height="48" />
    </form>
</body>

</html>
```

**输出:**
![](img/1b9f70903dfcb39d74ad9d53adaedeb8.png)

**支持的浏览器:**T2 HTML<输入> src 属性支持的浏览器如下:

*   谷歌 Chrome 1.0
*   Internet Explorer 2.0
*   Firefox 1.0
*   苹果 Safari 1.0
*   Opera 1.0