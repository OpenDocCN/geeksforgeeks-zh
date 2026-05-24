# jQuery |:文件选择器

> 原文:[https://www.geeksforgeeks.org/jquery-file-selector/](https://www.geeksforgeeks.org/jquery-file-selector/)

**:文件选择器**用于选择具有文件字段的输入元素。**(类型= =文件)**

**语法:**

```html
$(":file")
```

**示例:**类型=文件的输入元素。

```html
<!DOCTYPE html>
<html>

<head>
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
  </script>
    <script>
        $(document).ready(function() {
            $(":file").css("background-color", 
                           "dodgerblue");
        });
    </script>
</head>

<body>
    <center>
        <h1 style="color:green;">GeeksForGeeks
      </h1>
        <h2>jQuery :file Selector</h2>

        <form action="">
            Name:
            <input type="text"
                   name="user">
            <br> Password:
            <input type="password" 
                   name="password">
            <br> File:
            <input type="file"
                   name="myfile">
        </form>
  </center>
</body>

</html>
```

**输出:**
![](img/c566a177808e197f95620c640321a6b7.png)

**支持的浏览器:**T2 jQuery:文件选择器支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队