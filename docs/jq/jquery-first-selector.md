# jQuery |:第一选择器

> 原文:[https://www.geeksforgeeks.org/jquery-first-selector/](https://www.geeksforgeeks.org/jquery-first-selector/)

它是一个 **jQuery 选择器**，用于选择指定类型的第一个元素。

**语法:**

```html
$(":first")
```

**返回值:**选择并返回第一个元素。

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
            $("p:first").css(
              "background-color", "green");
        });
    </script>
</head>

<body>

    <p>Geeks for Geeks</p>
    <p>jQuery</p>
    <p>First Selector</p>

</body>

</html>
```

**输出:**
![](img/0d5d8ad2cda5a87057b4ce37b567eac0.png)

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
            $("p:first").css(
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
        <p>First Selector</p>
    </div>

    <p>jQuery:First Selector</p>

</body>

</html>
```

**输出:**
![](img/8dac78327734cd71840aa1c916273dc6.png)

**注意:**以上代码将只选择第一个 div 的第一个< p >元素。要选择第二个 div 的第一个< p >元素，请使用:第一个子选择器。

**支持的浏览器:**

*   谷歌 Chrome 90.0+
*   Internet Explorer 9.0
*   Firefox 3.6
*   Safari 4.0
*   歌剧 10.5