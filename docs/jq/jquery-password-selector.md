# jQuery |:密码选择器

> 原文:[https://www.geeksforgeeks.org/jquery-password-selector/](https://www.geeksforgeeks.org/jquery-password-selector/)

**:密码选择器**用于选择具有密码字段的输入元素。即**(类型= =密码)**

**语法:**

```html
$(":password")
```

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
  </script>

  <script>
      $(document).ready(function() {
         $(":password").css("background-color", 
                               "green");
        });
    </script>
</head>

<body>
    <center>
        <h1 style="color:green;">
          GeeksForGeeks
      </h1>
        <h2>jQuery :password Selector
      </h2>

        <form action="">
            Name:
            <input type="text"
                   name="user">
            <br> Password:
            <input type="password" 
                   name="password">
            <br>
            <br>
            <input type="reset" 
                   value="Reset">
            <input type="submit"
                   value="Submit">
            <br>
        </form>

</body>

</html>
```

**输出:**
![](img/7fd1b80b019081a51b3bdb9348bcc015.png)

**支持的浏览器:**T2 jQuery:密码选择器支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队