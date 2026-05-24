# HTML | DOM 图像自然高度属性

> 原文:[https://www . geesforgeks . org/html-DOM-image-natural height-property/](https://www.geeksforgeeks.org/html-dom-image-naturalheight-property/)

**自然高度:**此属性用于获取图像的原始高度。由于要在网页上显示的图像的高度可以使用< img >标签中的“高度”属性进行修改，因此自然高度属性在需要图像的原始高度而不是定制高度并且它是只读属性的情况下变得有用。

**语法:**

```html
*imageObject*.naturalHeight

```

**返回值:**以像素为单位返回图像的原始高度。

**示例:**

```html
<html>

<body>
    <center>
        <img src=
             "https://media.geeksforgeeks.org/wp-content/uploads/20190602171808/629-300x255.png" 
             id="image" alt="" width="250" height="205" 
             class="alignnone size-medium wp-image-1092360" />
        <br>
        <br>
        <button type="button" onclick="getHeight()">Click</button>
        <div id="text"></div>
    </center>
    <script>
        function getHeight() {
            var imgObject = document.getElementById("image");
            var output = document.getElementById("text");
            output.innerHTML = "Height of image: " + imgObject.height +
                "<br>naturalHeight of image: " + imgObject.naturalHeight;
        }
    </script>
</body>

</html>
```

**输出:**
**点击前:**
![](img/73f81c00e8c2ca56f7387fb3088ae201.png)
**点击后:**
![](img/aa3ffff98a0258438f08b32db9bb0e92.png)

**Supported browsers :**

*   谷歌 Chrome*   Internet Explorer 9.0 或更高版本*   Mozilla Firefox*   旅行队*   歌剧