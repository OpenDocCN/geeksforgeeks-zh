# 如何在 HTML5 中制作影像地图？

> 原文:[https://www . geesforgeks . org/如何制作 html5 中的图像地图/](https://www.geeksforgeeks.org/how-to-make-image-maps-in-html5/)

HTML [**<地图>**](https://www.geeksforgeeks.org/html-map-tag/) 标签用于在 HTML 中定义图像地图。图像内可点击的区域使用 [**<区域>**](https://www.geeksforgeeks.org/html-area-tag/) 标签定义。

**语法:**

```html
<map name="map-name">
```

**属性值:**

*   **名称:**用于将地图与其使用的图像关联起来。

**注意:**地图中的**名称**属性必须与图像的 [**属性具有相同的值，使用地图**](https://www.geeksforgeeks.org/html-area-tag/) 属性。

**示例:**在本例中，突出显示的区域是映射的区域，点击它将指向网站。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible"
        content="IE=edge">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0">    
</head>
<body>
    <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/array-2.png"
        alt="gfgimage" usemap="#mapID">

    <map name="mapID">
        <area shape="rect" 
            coords="34, 44, 270, 350"
href="https://www.geeksforgeeks.org/data-structures/?ref=shm">
    </map>
</body>
</html>
```

**输出:**

![](img/eed0bf49a91934e1ce7fab7fd7a491e7.png)