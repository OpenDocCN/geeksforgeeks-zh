# HTML | DOM 有属性()方法

> 原文:[https://www . geesforgeks . org/html-DOM-hasattributes-method/](https://www.geeksforgeeks.org/html-dom-hasattributes-method/)

**DOM hasAttribute()** 方法是一个布尔函数，它返回真或假，但不能同时返回真和假。如果元素包含属性，此方法返回真值，否则返回假值。知道文档中的元素是否有属性非常有用。

**语法:**

```html
node.hasAttributes()
```

**参数:**不包含任何参数。

**返回值:**如果元素包含属性则返回真，否则返回假。

**例 1:**

```html
<!DOCTYPE html> 
<html> 
    <head> 
        <title>
            DOM hasAttributes() Method
        </title> 
    </head> 

    <body> 
        <center> 
            <h1 style = "color:green;width:50%;" id = "sudo"> 
                GeeksForGeeks 
            </h1> 

            <h2>DOM hasAttributes() Method </h2>     

            <p>Click on the button to check if that body 
            element has any attributes</p>

            <button type = "button" onclick = "geeks()"> 
                Submit 
            </button> 

            <script> 
                function geeks() { 
                    var s = document.body.hasAttributes();
                    document.getElementById('gfg').innerHTML = s;
                } 
            </script> 

            <p id = "gfg"></p>
        </center> 
    </body> 
</html>                                
```

**输出:**
**点击按钮前:**
![](img/f909cad4235e8e532e108737e2fd4de4.png)
**点击按钮后:**
![](img/0a2f52abbad60f05630dc13c7cf558b9.png)

**例 2:**

```html
<!DOCTYPE html> 
<html> 
    <head id = "rk"> 
        <title>
            DOM hasAttributes() Method
        </title> 
    </head> 

    <body> 
        <center> 
            <h1 style = "color:green;width:50%;" id = "sudo"> 
                GeeksForGeeks 
            </h1> 

            <h2>DOM hasAttributes() Method </h2>

            <p>Click on the button to check if that
            head element has any attributes</p>     

            <button type = "button" onclick = "geeks()"> 
                Submit 
            </button> 

            <script> 
                function geeks() { 
                    var s = document.head.hasAttributes();
                    document.getElementById('gfg').innerHTML = s;
                } 
            </script> 
                <p id = "gfg"></p>
        </center> 
    </body> 
</html>                    
```

**输出:**
**点击按钮前:**
![](img/8a134b2f493b14dfce1cd8f70cdb39fc.png)
**点击按钮后:**
![](img/fd28d15f2169cd3ec458305f95ec4283.png)

**支持的浏览器:**T2 DOM has attributes()方法支持的浏览器如下:

*   谷歌 Chrome
*   Internet Explorer 9.0
*   火狐浏览器
*   歌剧
*   旅行队