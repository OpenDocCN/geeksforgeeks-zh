# SVG 文档图像属性

> 原文:[https://www.geeksforgeeks.org/svg-document-image-property/](https://www.geeksforgeeks.org/svg-document-image-property/)

SVG `<em>` Document.image 属性返回当前 HTML 文档中的图像集合。

**语法:**

```html
var imageCollection = document.images

```

**返回值:**该属性返回当前 HTML 文档中的图像集合。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <img src="https://media.geeksforgeeks.org/wp-content/
        cdn-uploads/20200817185016/gfg_complete_logo_2x-min.png">

    <svg width="700" height="500" 
        xmlns="http://www.w3.org/2000/svg">

        <script>
            console.log(document.images);    
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/d4e9599dcb3521739d65dada3a67a925.png)