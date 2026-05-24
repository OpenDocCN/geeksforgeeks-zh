# HTML | DOM 锚点目标属性

> 原文:[https://www . geesforgeks . org/html-DOM-anchor-target-property/](https://www.geeksforgeeks.org/html-dom-anchor-target-property/)

HTML DOM 中的**锚点目标属性**用于设置或返回链接的目标属性值。**目标属性**用于指定打开链接的位置。

**语法:**

*   它返回目标属性。

    ```html
    anchorObject.target
    ```

*   它用于设置目标属性。

    ```html
    anchorObject.target = "_blank|_self|_parent|_top|framename" 
    ```

**属性值:**

*   **_blank:** 在新窗口打开链接。
*   **_self:** 在同一框架中打开链接的文档。
*   **_parent:** 打开父框架集中的链接文档。
*   **_top:** 在窗口的整个正文中打开链接的文档。
*   **框架名称:**在命名框架中打开链接文档。

**返回值:**返回代表链接文档目标的字符串值。

**示例 1:** 本示例返回锚点目标属性。

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        HTML DOM Anchor target Property 
    </title> 
</head> 

<body> 
    <center> 
        <h1>GeeksForGeeks</h1> 

        <h2>DOM Anchor Target Property</h2> 

        <p>Welcome to 
            <a href = 
"https://manaschhabra:manaschhabra499@www.geeksforgeeks.org/" 
            id="GFG" target= "_self"> 
                GeeksforGeeks 
            </a> 
        </p> 

        <button onclick = "myGeeks()">Submit</button> 

        <p id = "sudo" style="color:green;font-size:25px;"></p> 

        <!-- Script to return Anchor Target Property -->
        <script> 
            function myGeeks() { 
                var x = document.getElementById("GFG").target; 
                document.getElementById("sudo").innerHTML = x; 
            } 
        </script>
    </center> 
</body> 

</html>
```

输出:
**点击按钮前:**
![](img/033965890cd6795d28d7db68ba9c85a7.png)
**点击按钮后:**
![](img/3e3f89e09c027c224d09a77966156456.png)

**示例 2:** 本示例设置锚点目标属性。

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        HTML DOM Anchor target Property 
    </title> 
</head> 

<body> 
    <center> 
        <h1>GeeksForGeeks</h1> 

        <h2>DOM Anchor Target Property</h2> 

        <p>Welcome to 
            <a href = 
"https://manaschhabra:manaschhabra499@www.geeksforgeeks.org/"
            id="GFG" target= "_self"> 
                GeeksforGeeks 
            </a> 
        </p> 

        <button onclick = "myGeeks()">Submit</button> 

        <p id = "sudo" style="color:green;font-size:25px;"></p> 

        <!-- Script to set Anchor Target Property -->
        <script> 
            function myGeeks() { 
                var x = document.getElementById("GFG").target
                        = "_blank"; 

                document.getElementById("sudo").innerHTML
                        = "The value of the target attribute "
                        + "was changed to " + x; 
            } 
        </script>
    </center> 
</body> 

</html>            
```

**输出:**
**点击按钮前:**
![](img/033965890cd6795d28d7db68ba9c85a7.png)
**点击按钮后:**
![](img/5fab9100bf712fa5324a5f6e64e1531a.png)

**支持的浏览器:****DOM Anchor Target 属性**支持的浏览器如下:

*   谷歌 Chrome
*   Internet Explorer 10.0 +
*   火狐浏览器
*   歌剧
*   旅行队