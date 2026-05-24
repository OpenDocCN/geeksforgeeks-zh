# HTML |  ismap 属性

> 原文:[https://www.geeksforgeeks.org/html-img-ismap-attribute/](https://www.geeksforgeeks.org/html-img-ismap-attribute/)

**HTML < img >是一个布尔属性。当存在时，它指定图像是服务器端图像映射的组成元素(图像映射是具有可点击区域的图片)。当单击服务器端图像地图时，印刷机坐标平方度量作为网址查询字符串发送到服务器。**

**语法:**

```html
<img ismap>
```

**示例:**

```html
<!DOCTYPE html>
<html>

<body>
    <center>
        <h1 style="color:green"> 
            GeeksforGeeks 
        </h1>
        <h2>HTML ismap Attribute</h2>
        <a href="#">
            <img src="img3.png"
                 alt="GFG.com"
                 width="400" 
                 height="150"
                 ismap>
        </a>
    </center>
</body>

</html>
```

**输出:**
**点击图像前:**
![](img/e42980ea552dec3d797ad6040fb057d0.png)

**点击图像后:**
![](img/263fb71a54c7c7252d4c55536382c46f.png)

**支持的浏览器:**以下是 **< img > ismap 属性**支持的浏览器:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧