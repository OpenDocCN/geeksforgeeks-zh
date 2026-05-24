# 如何使用 HTML5 为外部(非 HTML)应用定义容器？

> 原文:[https://www . geesforgeks . org/如何使用 html5 定义外部非 html 应用程序的容器/](https://www.geeksforgeeks.org/how-to-define-a-container-for-an-external-non-html-application-using-html5/)

本文的方法是使用文档中的<embed>元素为外部应用程序定义一个容器。这用于嵌入外部应用程序，通常是像音频或视频这样的多媒体内容。

它被用作嵌入插件(如 flash 动画)的容器。

**语法:**

```html
<embed attributes>
```

**示例:**下面的代码说明了如何将视频应用程序嵌入到您的文档中。

```html
<!DOCTYPE html> 
<html> 
    <head> 
        <title>
Define a container for an external (non-HTML) application
       </title> 
        <style> 
            q { 
                color: #00cc00; 
                font-style: italic; 
            } 
        </style> 
    </head> 
    <body> 

        <br> 
        <embed src="loading2.swf"
        type="application/x-shockwave-flash"> 
    </body> 
</html>
```

**输出:**
![](img/ef08231e7db02f032cb0663c20d720c2.png)

**支持的浏览器:**

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧