# HTML | DOM 锚点类型属性

> 原文:[https://www . geesforgeks . org/html-DOM-anchor-type-property/](https://www.geeksforgeeks.org/html-dom-anchor-type-property/)

HTML DOM 中的**锚点类型属性**用于设置或返回链接的类型属性值。类型属性用于指定目标网址的 MIME 类型，通常纯粹是建议性的。

**语法:**

*   它返回锚类型属性。

    ```html
    anchorObject.type 
    ```

*   用于设置锚类型属性。

    ```html
    anchorObject.type = MIME-type 
    ```

**属性值:**包含单值 **MIME 类型**，用于指定目标网址。

**返回值:**返回一个字符串值，代表链接文档的 MIME 类型。

**示例 1:** 本示例返回锚类型属性。

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        HTML DOM Anchor type Property 
    </title> 
</head> 

<body> 
    <center> 
        <h1>GeeksForGeeks</h1> 

        <h2>DOM Anchor type Property</h2> 

        <p>Welcome to 
            <a href = 
"https://manaschhabra:manaschhabra499@www.geeksforgeeks.org/" 
            id="GFG" type="text/html"> 
                GeeksforGeeks 
            </a> 
        </p> 

        <button onclick = "myGeeks()">Submit</button> 

        <p id = "sudo" style="color:green;font-size:25px;"></p> 

        <!-- Script to return Anchor type Property -->
        <script> 
            function myGeeks() { 
                var x = document.getElementById("GFG").type; 
                document.getElementById("sudo").innerHTML = x; 
            } 
        </script>
    </center> 
</body> 

</html>                    
```

**输出:**
**点击按钮前:**
![](img/5a245361cedd36484635d9916b4abe17.png)
**点击按钮后:**
![](img/d73ec256b048f3fc56d1368fac44b4fb.png)

**示例 2:** 本示例设置锚点类型属性。

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        HTML DOM Anchor type Property 
    </title> 
</head> 

<body> 
    <center> 
        <h1>GeeksForGeeks</h1> 

        <h2>DOM Anchor type Property</h2> 

        <p>Welcome to 
            <a href = 
"https://manaschhabra:manaschhabra499@www.geeksforgeeks.org/" 
            id="GFG"> 
                GeeksforGeeks 
            </a> 
        </p> 

        <button onclick = "myGeeks()">Submit</button> 

        <p id = "sudo" style="color:green;font-size:25px;"></p> 

        <!-- Script to set Anchor type Property -->
        <script> 
            function myGeeks() { 
                var x = document.getElementById("GFG").type
                        = "text/html"; 

                document.getElementById("sudo").innerHTML
                        = "The value of the type attribute of"
                        + " above linke is " + x; 
            } 
        </script>
    </center> 
</body> 

</html>                    
```

**输出:**
**点击按钮前:**
![](img/5a245361cedd36484635d9916b4abe17.png)
**点击按钮后:**
![](img/7bdbcf3bf2d99f982eb90fb2e54a8022.png)

**支持的浏览器:****DOM Anchor 类型属性**支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队