# 网页 API HTMLBodyElement.background 属性

> 原文:[https://www . geesforgeks . org/web-API-html body element-background-property/](https://www.geeksforgeeks.org/web-api-htmlbodyelement-background-property/)

背景属性用于返回一个表示背景图像资源位置描述的多字符串。

**语法:**

```html
BodyElement.background
```

**返回值:**该属性返回一个表示背景图像资源位置描述的 DOMString 。

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html> 
<html> 

<!-- body tag starts here -->
<body background= 
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png"> 

    <center> 
        <h1>GeeksforGeeks</h1> 
        <h2>HTMLBodyElement.background Property</h2> 

    </center>  
    <script type="text/javascript">
        console.log("body background URL is : ",document.body.background);
    </script>
</body>

</html>
```

**输出:**

![](img/22c07bebcb049efe0be12460cf6f6b0c.png)

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html> 
<html> 

<!-- body tag starts here -->
<body background= 
    "https://media.geeksforgeeks.org/wp-content/uploads/rk.png"> 

    <center> 
        <h1>GeeksforGeeks</h1> 
        <h2>HTMLBodyElement.background Property</h2> 

    </center>  
    <script type="text/javascript">
        console.log(document.body.background);
    </script>
</body>

</html>
```

**输出:**

![](img/423d4951453e9417b7a894c09a2046f2.png)

**支持的浏览器:**

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧