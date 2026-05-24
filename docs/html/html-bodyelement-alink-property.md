# HTML BodyElement.aLink 属性

> 原文:[https://www . geesforgeks . org/html-body element-alink-property/](https://www.geeksforgeeks.org/html-bodyelement-alink-property/)

**HTML BodyElement.aLink 属性**用于返回一个表示活动超链接颜色的 DOMString

**语法:**

```html
BodyElement.aLink
```

**返回值:**该属性返回一个表示活动超链接颜色的多字符串

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html> 
<html> 

<!-- body tag starts here -->
<body aLink = "green">

    <center> 
        <h1>GeeksforGeeks</h1> 
        <h2>HTMLBodyElement.aLink Property</h2> 

        <a href = "#"> 
            A computer science 
            portal for geeks 
        </a> 
    </center>  

    <script type = "text/javascript">
        console.log(document.body.aLink);
    </script>
</body>

</html>
```

**输出:**

![](img/e8e052f9ad3b29b7891f1747d401a986.png)

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html> 
<html> 

<!-- body tag starts here -->
<body aLink = "red">

    <center> 
        <h1>GeeksforGeeks</h1> 
        <h2>HTMLBodyElement.aLink Property</h2> 

        <a href = "#"> 
            A computer science 
            portal for geeks 
        </a> 
    </center>  

    <script type = "text/javascript">
        console.log(document.body.aLink);
    </script>
</body>

</html>
```

**输出:**

![](img/ea0f3bbc52ad60fc610b17a7e508078d.png)

**支持的浏览器:**

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧
*   边缘