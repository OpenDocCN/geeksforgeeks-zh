# jquery | isemptyoobject()方法

> 原文:[https://www.geeksforgeeks.org/jquery-isemptyobject-method/](https://www.geeksforgeeks.org/jquery-isemptyobject-method/)

jQuery 中的这个 **isEmptyObject()** 方法用来判断一个对象是否为空。

**语法:**

```html
jQuery.isEmptyObject( object )

```

**参数:**isEmptyObject()方法只接受上面提到的一个参数，如下所述:

*   **对象:**此参数是将被检查是否为空的对象。

**返回值:**返回布尔值。

下面的例子说明了 isEmptyObject()方法在 jQuery 中的使用:

**示例 1:** 在本例中， **isEmptyObject()方法**检查对象是否为空。

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>JQuery | isEmptyObject() method</title> 
<script src="https://code.jquery.com/jquery-3.4.1.js"></script>

</head>
<body style="text-align:center;"> 

    <h1 style="color: green"> 
        GeeksForGeeks 
    </h1> 

    <h3>JQuery | isEmptyObject() method</h3>
    <b>Whether '{}' is a Empty Object : </b>
    <p></p>

    <script>
    $( "p" ).append( "" + $.isEmptyObject({}));
    </script>
</body>
</html>                                                                        
```

**输出:**
![](img/8ca77b34ca48fd3129111311f84d24d0.png)

**示例 2:** 在本例中， **isEmptyObject()方法**还会检查对象是否为空。

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>JQuery | isEmptyObject() method</title> 
<script src="https://code.jquery.com/jquery-3.4.1.js"></script>

</head>
<body style="text-align:center;"> 

    <h1 style="color: green"> 
        GeeksForGeeks 
    </h1> 

    <h3>JQuery | isEmptyObject() method</h3>
    <b>Whether String is a Empty Object : </b>
    <p id ="gfg"></p>
    <b>Whether Array is a Empty Object : </b>
    <p id ="gfg1"></p>

    <script>
    // string ="Shubham"
    $( "#gfg" ).append( "Shubham : " + $.isEmptyObject("Shubham"));

    // array
    $( "#gfg1" ).append( 
"[1, 3, 4, 6, 8] : " + $.isEmptyObject([1, 3, 4, 6, 8]));

    </script>
</body>
</html>                                                                                                                    
```

**输出:**
![](img/d0d09bcefde35bd370ecfd416b8783c3.png)