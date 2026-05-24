# JQuery | globalEval()方法

> 原文:[https://www.geeksforgeeks.org/jquery-globaleval-method/](https://www.geeksforgeeks.org/jquery-globaleval-method/)

jQuery 中的这个 **globalEval()** 方法是用来全局执行一些 JavaScript 代码的。

**语法:**

```html
jQuery.globalEval( code [, options ] )

```

**参数:**global eval()方法接受上面提到的和下面描述的两个参数:

*   **代码:**这个参数是要执行的 JavaScript 代码。
*   **选项= > nonce :** 此参数是传递给执行脚本的 nonce 属性。

**返回值:**返回布尔值。

以下示例说明了在 jQuery 中使用 globalEval()方法:

**示例 1:** 在本例中， **globalEval()方法**在全局上下文中执行脚本。

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>JQuery | globalEval() method</title> 
<script src="https://code.jquery.com/jquery-3.4.1.js"></script>

</head>
<body style="text-align:center;"> 

    <h1 style="color: green"> 
        GeeksForGeeks 
    </h1> 

    <h3>JQuery | globalEval() method</h3>
    <p>Execute a script in the global context.</p>
    <p id = "geeks"> </p>
    <script>
    function GFG() {
      jQuery.globalEval( "var newVar = 'Shubham Singh'" );
      document.getElementById("geeks").innerHTML = newVar;
    }
    GFG();
    </script>
</body>
</html>                                                                                                    
```

**输出:**
![](img/f32d4a76cb6af0dade77af9b32e5deda.png)

**示例 2:** 在此示例中， **globalEval()方法**在启用了内容安全策略的站点上执行带有随机数的脚本。

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>JQuery | globalEval() method</title> 
<script src="https://code.jquery.com/jquery-3.4.1.js"></script>

</head>
<body style="text-align:center;"> 

    <h1 style="color: green"> 
        GeeksForGeeks 
    </h1> 

    <h3>JQuery | globalEval() method</h3>
    <p>Execute a script with a nonce value on a<br>
    site with Content Security Policy enabled.</p>
    <p id = "geeks"> </p>
    <script>
    function GFG() {
      jQuery.globalEval( "var variable = true;", {
    nonce: "nonce-2726c7f26c"
  } );
      document.getElementById("geeks").innerHTML = variable;
    }
    GFG();
    </script>
</body>
</html>                                                                                                                                            
```

**输出:**
![](img/95bf95a5f21d9ac9c595de8f26269176.png)