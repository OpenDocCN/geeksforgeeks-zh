# CSS | url()函数

> 原文:[https://www.geeksforgeeks.org/css-url-function/](https://www.geeksforgeeks.org/css-url-function/)

**url()函数**是一个内置函数，用于包含一个文件。这个函数的参数是绝对网址、相对网址或数据 URI。url()函数可用于背景图像、边框图像、列表样式图像、内容、光标、边框图像、边框图像源、作为@font-face 块一部分的 src 和@counter-style/symbol。

**语法:**

```html
url( <string> <url-modifier>* )
```

**参数:**该函数接受单参数**网址**，该网址以字符串形式保存网址。网址的例子有:

```html
<css_property>: url("https://geeksforgeeks.org/image.png")
<css_property>: url('https://geeksforgeeks.org/image.png')
<css_property>: url(https://geeksforgeeks.org/image.png)

```

下面的例子说明了 CSS 中的 url()函数:

**示例:**

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title>CSS url() function</title> 

    <style>
        body {
            background-image: url(
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png");
            text-align:center;
        }
        h1 {
            color:white;
        }
    </style> 
</head> 

<body> 
    <h1>GeeksforGeeks</h1>
    <h2>CSS url() function</h2>
</body> 

</html>    
```

**输出:**
![](img/4e078e2dd04d916c4fd0e834f583663f.png)

**支持的浏览器:**URL()函数支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧