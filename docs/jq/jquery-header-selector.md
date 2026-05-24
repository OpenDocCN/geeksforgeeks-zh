# jQuery |:表头选择器

> 原文:[https://www.geeksforgeeks.org/jquery-header-selector/](https://www.geeksforgeeks.org/jquery-header-selector/)

**:标题选择器**用于选择从 **( < h1 >到< h6 > )** 的所有标题元素。

**语法:**

```html
$(":header") 
```

**示例:**将所有标题的颜色改为绿色。

```html
<!DOCTYPE html>
<html>

<head>
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
    <script>
        $(document).ready(function() {
            $(":header").css(
                "color", "green");
        });
    </script>
</head>

<body>
    <center>
        <h1>GeeksForGeeks</h1>
        <h2>jQuery :header Selector
      </h2>

        <div style="color:orange;">
            GeeksForGeeks
        </div>
        <h5>A computer science 
          portal for geeks.
      </h5>
        <p style="color:dodgerblue">
            Sudo Placement
        </p>
        <p>GFG</p>
    </center>
</body>

</html>
```

**输出:**
![](img/b6f1020db206b922555edc3e61e0c1f0.png)

**支持的浏览器:**支持的浏览器 **jQuery:表头选择器**如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队