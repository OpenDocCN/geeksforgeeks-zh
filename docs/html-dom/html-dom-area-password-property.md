# HTML | DOM 区域密码属性

> 原文:[https://www . geesforgeks . org/html-DOM-area-password-property/](https://www.geeksforgeeks.org/html-dom-area-password-property/)

HTML DOM 中的区域密码属性用于设置或返回 href 属性的密码部分的值。它在用户名之后和主机名之前指定。
**例如:**https://manaschhabra:manaschhabra499@www.geeksforgeeks.org/(manachhabra 是用户名，manaschhabra499 是密码)。

**语法:**

*   它返回区域密码属性。

    ```html
     areaObject.password
    ```

*   它用于设置区域密码属性。

    ```html
    areaObject.password = password
    ```

**属性值:**它包含指定网址密码部分的单个值。

**返回值:**返回一个字符串值，代表网址的密码部分。

**示例 1:** 本示例返回区域密码属性。

```html
<!DOCTYPE html> 
<html> 
<title> 
    HTML DOM Area password Property 
</title> 

<body> 
    <h4> HTML DOM Area password Property </h4> 
    <button onclick="GFG()">Click Here! 
    </button> 
    <map name="Geeks1"> 
        <area id="Geeks"
            shape="rect"
            coords="0, 0, 110, 100"
            alt="Geeks"
            href= 
        https://manaschhabra:manaschhabra499@www.geeksforgeeks.org/
    </map> 

    <img src= 
"https://media.geeksforgeeks.org/wp-content/uploads/a1-25.png"
        width="300"
        height="100"
        alt="Geeksforgeeks"
        usemap="#Geeks1"> 
    </br>
    <p id="GEEK!"></p> 

    <script> 
        function GFG() { 

        // Return password property. 
            var x = document.getElementById("Geeks").password; 
        document.getElementById("GEEK!").innerHTML = x; 
        } 
    </script> 
</body> 

</html>                    
```

**输出:**
点击按钮前:
![](img/89825bdb45f8a6033b792cd28d351d45.png)

点击按钮后:
![](img/33afa7daf6d2c34ef56eccc327330f60.png)
 **示例 2:** 本示例设置区域密码属性。

```html
<!DOCTYPE html> 
<html> 
<title> 
    HTML DOM Area password Property 
</title> 

<body> 
    <h4> HTML DOM Area password Property </h4> 
    <button onclick="GFG()">Click Here! 
    </button> 
    <map name="Geeks1"> 
        <area id="Geeks"
            shape="rect"
            coords="0, 0, 110, 100"
            alt="Geeks"
            href= 
        https://manaschhabra:manaschhabra499@www.geeksforgeeks.org/
    </map> 

    <img src= 
"https://media.geeksforgeeks.org/wp-content/uploads/a1-25.png"
        width="300"
        height="100"
        alt="Geeksforgeeks"
        usemap="#Geeks1"> 
    </br>
    <p id="GEEK!"></p> 

    <script> 
        function GFG() { 

        // Sets password property. 
            var x = document.getElementById("Geeks").password = "abcxyz"; 
        document.getElementById("GEEK!").innerHTML = 
                "The password has been changed to " + x; 
        } 
    </script> 
</body> 

</html>                     
```

**输出:**
点击按钮前:
![](img/89825bdb45f8a6033b792cd28d351d45.png)

点击按钮后:
![](img/6313cbfa8a70b75d14cd013804eb2476.png)

**支持的浏览器:**

*   谷歌 Chrome
*   火狐浏览器
*   歌剧