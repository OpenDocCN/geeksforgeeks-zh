# HTML | frameset cols 属性

> 原文:[https://www.geeksforgeeks.org/html-frameset-cols-attribute/](https://www.geeksforgeeks.org/html-frameset-cols-attribute/)

**HTML <框架集>列属性**用于*指定框架集*的大小和列数。每一帧的宽度用逗号分隔。

**语法:**

```html
<frameset cols="pixels | % | *">
```

**属性值:**

*   **像素:**以像素为单位设置列宽。例如:**“50px”**或**“50”**。
*   **%:** 列宽按百分比设置。例**“70%”**。
*   ***:** 列宽设置为所有可用空间。

**示例:**

```html
<!DOCTYPE html> 
<html>     
    <head> 
        <title>HTML frameset cols Attribute</title> 
    </head> 

    <frameset cols = "30%, 40%, 30%"> 
        <frame name = "top" src = "attr1.png" /> 
        <frame name = "main" src = "gradient3.png" /> 
        <frame name = "bottom" src = "col_last.png" />         
    </frameset> 
</html>
```

**输出:**
![](img/007aa7a67f60d7c58f5c77af6ac290c4.png)

**支持的浏览器:**支持的浏览器 **HTML <框架集> cols 属性**如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧