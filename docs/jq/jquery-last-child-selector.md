# jQuery |:最后一个子选择器

> 原文:[https://www.geeksforgeeks.org/jquery-last-child-selector/](https://www.geeksforgeeks.org/jquery-last-child-selector/)

这是一个 **jQuery 选择器**，用于选择其**父级**的**最后一个子级**的每个元素。

**语法:**

```html
$(":last-child")
```

**返回值:**选择并返回其父元素的最后一个子元素。

**示例-1:**

```html
<!DOCTYPE html>
<html>
<h1>
  <center>
    Geeks 
  </center>
  </h1>

<head>
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
  </script>
    <script>
        $(document).ready(function() {
            $("p:last-child").css(
              "background-color", "green");
        });
    </script>
</head>

<body>
<div>
    <p>Geeks for Geeks</p>
    <p>jQuery</p>
    <p>Last Child Selector</p>
</div>
</body>

</html>
```

**输出:**
![](img/c4de323209f242b3cf59b038e9b5e284.png)

**示例-2:**

```html
<!DOCTYPE html>
<html>
<h1>
  <center>
    Geeks 
  </center>
  </h1>

<head>
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
  </script>

  <script>
        $(document).ready(function() {
            $("p:last-child").css(
              "background-color", "green");
        });
    </script>
</head>

<body>
    <div style="border:1px solid;">
        <p>Geeks for Geeks</p>
        <p>jQuery</p>
    </div>
    <br>

    <div style="border:1px solid;">
        <p>Geeks for Geeks</p>
        <p>jQuery</p>
        <p>Last Child Selector</p>
    </div>

    <p>jQuery:Last Child Selector</p>

</body>

</html>
```

**输出:**
![](img/14b4eb1cf9807ce896279ebab5a15e78.png)

**支持的浏览器:**

*   谷歌 Chrome 90.0+
*   Internet Explorer 9.0
*   Firefox 3.6
*   Safari 4.0
*   歌剧 10.5