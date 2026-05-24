# jQuery |。类别选择器

> 原文:[https://www.geeksforgeeks.org/jquery-class-selector/](https://www.geeksforgeeks.org/jquery-class-selector/)

**。类**选择器为要选择的元素指定类。它不应该以数字开头。它为几个 HTML 元素赋予了样式。

**语法:**

```html
$(".class")
```

**示例-1:**

```html
<!DOCTYPE html>
<html>

<head>
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
  </script>
    <script>
      $(document).ready(function() {
        $(".GEEKS").css("background-color"
                        , "pink");
        });
    </script>
</head>

<body>

    <p class="GEEKS">Geeks For Geeks
  </p>

    <span class="GEEKS">jQuery|.class selector
  </span>

</body>

</html>
```

**输出:**
![](img/8b2119b02749babb13966773afbde0a5.png)

**示例-2:**

```html
<!DOCTYPE html>
<html>

<head>
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
  </script>

  <script>
      $(document).ready(function() {
       $(".GEEKS").css("background-color",
                          "orange");
        });
    </script>
</head>

<body>

    <div style="border:2px solid red"
         class="GEEKS">
      Geeks For Geeks
  </div>
    <br>
    <br>

    <span class="GEEKS">jQuery|.class selector
  </span>

</body>

</html>
```

**输出:**
![](img/54270d967a4578cbe48b5f5e6f334b7a.png)

**支持的浏览器:**

*   谷歌 Chrome
*   Mozilla Firefox
*   边缘
*   旅行队
*   歌剧