# HTML 标签

> 哎哎哎:# t0]https://www . geeksforgeeks . org/html-img 标签/

HTML i **< img >** 标签用于在网页/网站内部添加图片。现在的网站不直接在网页上添加图像，因为图像是通过使用< img >标签链接到网页上的，该标签为图像保留空间。

**语法:**

```html
<img src="" alt="" width="" height="">
```

**属性:*****<img>*****标签具有以下属性。**

*   **[**src**](https://www.geeksforgeeks.org/html-img-src-attribute/) **:用于指定图像的路径。****
*   **[**alt**](https://www.geeksforgeeks.org/html-img-alt-attribute/) **:** 用于为图像指定替代文本。它非常有用，因为它可以通知用户图像的含义，并且由于任何网络问题，如果图像无法显示，则会显示该替代文本。**
*   ****crossorigin:** 用于导入第三方网站的图片，允许跨 origin 访问与 canvas 一起使用。**
*   **[**高度**](https://www.geeksforgeeks.org/html-img-height-attribute/) **:用于指定图像的高度。****
*   **[**宽度**](https://www.geeksforgeeks.org/html-img-width-attribute/) **:用于指定图像的宽度。****
*   **[**ismap**](https://www.geeksforgeeks.org/html-img-ismap-attribute/) **:** 用于指定一个图像作为服务器端图像映射。**
*   ****加载:**用于指定浏览器是应该推迟加载图像，直到满足某些条件，还是立即加载图像。**
*   ****longdesc:** 用于指定图片详细描述的 URL。**
*   ****推荐人策略**:用于指定取图时使用哪些推荐人信息，即*无推荐人、降级时无推荐人、产地、跨产地时产地、不安全网址。***
*   ****尺寸:**用于指定不同页面布局的图像尺寸。**
*   ****srcset:** 用于指定在不同情况下使用的图像文件列表。**
*   **[**使用地图**](https://www.geeksforgeeks.org/html-img-usemap-attribute/) **:** 用于指定图像作为客户端图像地图。**

****示例 1:** 在本例中，我们使用了**<img>标签以及[*src*](https://www.geeksforgeeks.org/html-img-src-attribute/)*宽度**高度*和 *alt* 属性。****

## ****超文本标记语言****

```html
**<!DOCTYPE html>
<html>

<body style="text-align: center;">
    <h3>GeeksforGeeks logo</h3>

    <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png"
        width="420" height="100" 
        alt="Geeksforgeeks.org">
</body>

</html>**
```

******输出:******

****![](img/1493d5304d32cb1214312ac4e8a63aa9.png)

带宽度和高度的 img src**** 

******示例 2:** 在本例中，我们添加了*样式*属性，为图像添加边框。****

## ****超文本标记语言****

```html
**<!DOCTYPE html>
<html>

<body style="text-align: center;">
    <h3>GeeksforGeeks logo</h3>

    <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png"
        width="420" height="100" 
        alt="Geeksforgeeks.org" 
        style="border:5px solid black">
</body>

</html>**
```

******输出:******

****![](img/4a3bd40c5ea4af608adf063f6e8105c6.png)

带边框的图像源**** 

******支持的浏览器:******

*   ****谷歌 Chrome****
*   ****微软公司出品的 web 浏览器****
*   ****旅行队****
*   ****歌剧****
*   ****火狐浏览器****