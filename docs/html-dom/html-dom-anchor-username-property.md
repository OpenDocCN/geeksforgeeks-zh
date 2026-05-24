# HTML | DOM 锚点用户名属性

> 原文:[https://www . geesforgeks . org/html-DOM-anchor-username-property/](https://www.geeksforgeeks.org/html-dom-anchor-username-property/)

HTML DOM 中的**锚点用户名属性**用于设置或返回 **href 属性**的用户名部分的值。用户名部分用于定义用户输入的用户名。它在协议之后和密码部分之前指定。
**例如:**https://manaschhabra:manaschhabra499@www.geeksforgeeks.org/(manachhabra 是用户名，manaschhabra499 是密码)。

**语法:**

*   它返回锚用户名属性。

    ```html
    anchorObject.username
    ```

*   它用于设置锚定用户名属性。

    ```html
    anchorObject.username = username
    ```

**属性值:**它包含单个值**用户名**，指定网址的用户名部分。

**返回值:**返回一个字符串值，代表网址的用户名部分。

**示例 1:** 本示例返回锚点用户名属性。

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        HTML DOM Anchor username Property 
    </title> 
</head> 

<body> 
    <center> 
        <h1>GeeksForGeeks</h1> 

        <h2>DOM Anchor username Property</h2> 

        <p>Welcome to 
            <a href = 
"https://manaschhabra:manaschhabra499@www.geeksforgeeks.org/" 
            id="GFG"> 
                GeeksforGeeks 
            </a> 
        </p> 

        <button onclick = "myGeeks()">Submit</button> 

        <p id = "sudo" style="color:green;font-size:25px;"></p> 

        <!-- Script to return Anchor username Property -->
        <script> 
            function myGeeks() { 
                var x = document.getElementById("GFG").username; 
                document.getElementById("sudo").innerHTML = x; 
            } 
        </script>
    </center> 
</body> 
</html>                    
```

**输出:**
**点击按钮前:**
![](img/61c6a0b4c3c698e6a3c1d5d11a951a01.png)
**点击按钮后:**
![](img/880b37b887dd848c486f38c03d8e6d6d.png)

**示例 2:** 本示例设置锚点用户名属性。

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        HTML DOM Anchor username Property 
    </title> 
</head> 

<body> 
    <center> 
        <h1>GeeksForGeeks</h1> 

        <h2>DOM Anchor username Property</h2> 

        <p>Welcome to 
            <a href = 
"https://manaschhabra:manaschhabra499@www.geeksforgeeks.org/" 
            id="GFG"> 
                GeeksforGeeks 
            </a> 
        </p> 

        <button onclick = "myGeeks()">Submit</button> 

        <p id = "sudo" style="color:green;font-size:25px;"></p> 

        <!-- Script to set Anchor username Property -->
        <script> 
            function myGeeks() { 
                var x = document.getElementById("GFG").username 
                            = "Harshitchhabra"; 

                document.getElementById("sudo").innerHTML
                        = "The username was changed to " + x; 
            } 
        </script>
    </center> 
</body>

</html>                    
```

**输出:**
**点击按钮前:**
![](img/61c6a0b4c3c698e6a3c1d5d11a951a01.png)
**点击按钮后:**
![](img/893073c02863e654d238140658c9dfc3.png)

**支持的浏览器:****DOM Anchor 用户名属性**支持的浏览器如下:

*   谷歌 Chrome
*   火狐浏览器
*   歌剧