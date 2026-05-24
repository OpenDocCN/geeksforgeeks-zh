# HTML | DOM 锚文本属性

> 原文:[https://www . geesforgeks . org/html-DOM-anchor-text-property/](https://www.geeksforgeeks.org/html-dom-anchor-text-property/)

HTML DOM 中的**锚文本属性**用于设置或返回链接的文本内容。

**语法:**

*   它返回锚文本属性。

    ```html
    anchorObject.text
    ```

*   它用于设置锚文本属性。

    ```html
    anchorObject.text = sometext
    ```

**属性值:**包含单个值**somethext**，指定链接字段的文本内容。

**返回值:**返回一个代表链接文本内容的字符串值。

**示例 1:** 本示例返回锚文本属性。

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        HTML DOM Anchor text Property 
    </title> 
</head> 

<body> 
    <center> 
        <h1>GeeksForGeeks</h1> 

        <h2>DOM Anchor text Property</h2> 

        <p>Welcome to 
            <a href = 
"https://manaschhabra:manaschhabra499@www.geeksforgeeks.org/" 
            id="GFG"> 
                GeeksforGeeks 
            </a> 
        </p> 

        <button onclick = "myGeeks()">Submit</button> 

        <p id = "sudo" style="color:green;font-size:25px;"></p> 

        <!-- Script to return Anchor text Property -->
        <script> 
            function myGeeks() { 
                var x = document.getElementById("GFG").text; 
                document.getElementById("sudo").innerHTML = x; 
            } 
        </script>
    </center> 
</body> 

</html>                    
```

**输出:**
**点击按钮前:**
![](img/3cebe204a081b1cecb2d38bdc6e974ff.png)
**点击按钮后:**
![](img/727d2445a4dd95454453c7d22591f6ba.png)

**示例 2:** 本示例设置锚文本属性。

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        HTML DOM Anchor text Property 
    </title> 
</head> 

<body> 
    <center> 
        <h1>GeeksForGeeks</h1> 

        <h2>DOM Anchor text Property</h2> 

        <p>Welcome to 
            <a href = 
"https://manaschhabra:manaschhabra499@www.geeksforgeeks.org/" 
            id="GFG"> 
                GeeksforGeeks 
            </a> 
        </p> 

        <button onclick = "myGeeks()">Submit</button> 

        <p id = "sudo" style="color:green;font-size:25px;"></p> 

        <!-- Script to set Anchor text Property -->
        <script> 
            function myGeeks() { 
                var x = document.getElementById("GFG").text
                        = "GFG"; 
                document.getElementById("sudo").innerHTML
                        = "The text was changed to " + x; 
            } 
        </script>
    </center> 
</body> 
</html>                    
```

**输出:**
**点击按钮前:**
![](img/3cebe204a081b1cecb2d38bdc6e974ff.png)
**点击按钮后:**
![](img/0a5511aa0a6c6b896062310cc427061e.png)

**支持的浏览器:****DOM 锚文本属性**支持的浏览器如下:

*   谷歌 Chrome
*   Internet Explorer 10.0 +
*   火狐浏览器
*   歌剧
*   旅行队