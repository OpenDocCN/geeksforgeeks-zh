# HTML | 目标属性

> 原文:[https://www.geeksforgeeks.org/html-base-target-attribute/](https://www.geeksforgeeks.org/html-base-target-attribute/)

HTML 中的 **<基>目标属性**用于指定网页中所有超链接和表单的默认目标。该属性也可以通过为每个超链接和表单使用目标属性来覆盖。

**语法:**

```html
<base target="_blank|_self|_parent|_top|framename" > 
```

**属性值:**

*   **_blank:** 在新窗口打开链接。
*   **_self:** 在同一框架中打开链接的文档。
*   **_parent:** 打开父框架集中的链接文档。
*   **_top:** 在窗口的整个正文中打开链接的文档。
*   **框架名称:**在命名框架中打开链接文档。

**示例:**此示例说明了目标属性在<基础>元素中的使用。

```html
<!DOCTYPE html> 
<html> 

<head> 
    <base target="_self"> 
    <title> 
        HTML Base target Attribute 
    </title> 
</head> 

<body style="text-align:center;"> 

    <h1 style="color:green;"> 
            GeeksForGeeks 
        </h1> 

    <h2>HTML Base target Attribute</h2> 

    <a href="ide.geeksforgeeks.org/" alt="GFG">
        Geeks Link
    </a>
</body> 

</html>                    
```

**输出:**
![](img/986862dbcd3d43b91a7ba0234cc7727b.png)

**支持的浏览器:***HTML 基础目标属性*支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧