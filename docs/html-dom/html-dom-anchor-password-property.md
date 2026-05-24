# HTML | DOM 锚点密码属性

> 原文:[https://www . geesforgeks . org/html-DOM-anchor-password-property/](https://www.geeksforgeeks.org/html-dom-anchor-password-property/)

HTML DOM 中的**锚点密码属性**用于设置或返回 **href 属性**值的密码部分。密码部分由用户在网址中输入，并在用户名和主机名之后指定。
**例如:**https://manaschh:manaschhabra499@www.geeksforgeeks.org/(manachh 是用户名，manaschhabra499 是密码)。

**语法:**

*   它返回锚定密码属性。

    ```html
    anchorObject.password
    ```

*   它用于设置锚定密码属性。

    ```html
    anchorObject.password = password
    ```

**属性值:**包含单值**密码**，指定网址的密码部分。

**返回值:**返回代表网址密码部分的字符串值。

**示例 1:** 本示例返回锚点密码属性。

```html
<!DOCTYPE html>
<html> 

<head> 
    <title> 
        HTML DOM Anchor Password Property 
    </title> 
</head> 

<body> 
    <center> 
        <h1>GeeksForGeeks</h1> 

        <h2>DOM Anchor Password Property</h2> 

        <p>Welcome to 
            <a href = 
"https://manaschh:manaschhabra499@www.geeksforgeeks.org/" 
            id="GFG"> 
                GeeksforGeeks 
            </a> 
        </p> 

        <button onclick = "myGeeks()">
            Submit
        </button> 

        <p id = "sudo" style="color:green;font-size:25px;"></p> 

        <!-- Script to return Anchor Password Property -->
        <script> 
            function myGeeks() { 
                var x = document.getElementById("GFG").password; 
                document.getElementById("sudo").innerHTML = x; 
            } 
        </script> 
    </center> 
</body> 

</html>                                               
```

**输出:**
**点击按钮前:**
![](img/83938831ea682c7a0bab545e38a25213.png)
**点击按钮后:**
![](img/7584806c1d843cc8f5807c42638fd035.png)

**示例 2:** 本示例设置锚点密码属性。

```html
<!DOCTYPE html>
<html> 

<head> 
    <title> 
        HTML DOM Anchor Password Property 
    </title> 
</head> 

<body> 
    <center> 
        <h1>GeeksForGeeks</h1> 

        <h2>DOM Anchor Password Property</h2> 

        <p>Welcome to 
            <a href = 
"https://manaschh:manaschhabra499@www.geeksforgeeks.org/" 
            id="GFG"> 
                GeeksforGeeks 
            </a> 
        </p> 

        <button onclick = "myGeeks()">
            Submit
        </button> 

        <p id = "sudo" style="color:green;font-size:25px;"></p> 

        <!-- Script to set Anchor Password Property -->
        <script> 
            function myGeeks() { 
                var x = document.getElementById("GFG").password
                        = "Password is changed now!"; 

                document.getElementById("sudo").innerHTML = x; 
            } 
        </script>
    </center> 
</body> 

</html>                    
```

**输出:**
**点击按钮前:**
![](img/83938831ea682c7a0bab545e38a25213.png)
**点击按钮后:**
![](img/511bb1d4842429d73ea47b364f229ddf.png)

**支持的浏览器:****DOM 锚点密码属性**支持的浏览器如下:

*   谷歌 Chrome
*   火狐浏览器
*   歌剧