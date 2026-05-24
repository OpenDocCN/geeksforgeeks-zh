# HTML | object 数据属性

> 原文:[https://www.geeksforgeeks.org/html-object-data-attribute/](https://www.geeksforgeeks.org/html-object-data-attribute/)

HTML 中的 **<对象>数据属性**用于指定对象的嵌入文件的 URL。

**语法:**

```html
<object data="URL">
```

**属性值:**包含单值 **URL** ，用于指定对象的来源。
网址的可能值有:

*   **绝对 URL:** 指向另一个网站。
*   **相对 URL:** 它指向网站内的一个文件。

**示例:**

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title>
        HTML <object>' data Attribute
    </title> 
</head> 

<body> 
    <center>
        <h1>GeeksForGeeks</h1> 

        <h1>
            HTML <object>data Attribute
        </h1> 
        <br> 

        <object data= 
"https://www.geeksforgeeks.org/wp-content/uploads/Geek_logi_-low_res.png"
                width="550px" height="150px"> 
            GeeksforGeeks 
        </object> 
    </center>
</body> 

</html>                    
```

**输出:**
![](img/e039b89a5b3591937d40a82a339cc94f.png)

**支持的浏览器:**以下是 **HTML <对象>数据属性**支持的浏览器:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队