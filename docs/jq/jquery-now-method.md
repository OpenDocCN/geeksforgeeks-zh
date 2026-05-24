# JQuery | now()方法

> 原文:[https://www.geeksforgeeks.org/jquery-now-method/](https://www.geeksforgeeks.org/jquery-now-method/)

jQuery 中的这个 **now()** 方法用来返回一个代表当前时间的数字。

**语法:**

```html
jQuery.now()

```

**参数:**now()方法不接受任何参数。

**返回值:**返回代表当前时间的数字。

**例 1:** 在本例中， **now()方法** a 用 **innerHTML** 功能显示毫秒数。

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>JQuery | now() method</title> 
<script src="https://code.jquery.com/jquery-3.4.1.js"></script>

</head>
<body style="text-align:center;"> 

    <h1 style="color: green"> 
        GeeksForGeeks 
    </h1> 

    <h3>JQuery | now() method</h3>
    <button onclick="geek()">Try it</button>

    <p id="demo"></p>

    <script>
    function geek() {
      var n = jQuery.now();
      document.getElementById("demo").innerHTML = n/3600;
    }
    </script>
</body>
</html>                                                                                            
```

**输出:**
**点击前:**
![](img/e5f00a32600a722cd3eb143c4b8edeef.png)
**点击后:**
![](img/8260e72821ef68007dd541a0c08de15c.png)

**例 2:** 在本例中， **now()方法** a 用**提醒**功能显示毫秒数。

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>JQuery | now() method</title> 
<script src="https://code.jquery.com/jquery-3.4.1.js"></script>

</head>
<body style="text-align:center;"> 

    <h1 style="color: green"> 
        GeeksForGeeks 
    </h1> 

    <h3>JQuery | now() method</h3>
    <button onclick="geek()">Try it</button>

    <script>
    function geek() {
      var n = jQuery.now();
      alert("Number of milliseconds : " + n);
    }
    </script>
</body>
</html>                                        
```

**输出:**
**点击前:**
![](img/a9390f649a9155a6509b7fa6c3ed4b74.png)
**点击后:**
![](img/847d8420f0ae8ce8b0cf511f9908cc26.png)