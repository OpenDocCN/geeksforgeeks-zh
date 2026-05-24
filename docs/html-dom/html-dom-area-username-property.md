# HTML | DOM 区域用户名属性

> 原文:[https://www . geesforgeks . org/html-DOM-area-username-property/](https://www.geeksforgeeks.org/html-dom-area-username-property/)

HTML DOM 中的区域用户名属性用于设置或返回 href 属性的用户名部分的值。用户名部分用于定义用户输入的用户名。它在协议之后和密码部分之前指定。
**例如:**https://manaschhabra:manaschhabra499@www.geeksforgeeks.org/(manachhabra 是用户名，manaschhabra499 是密码)。

**语法:**

*   它返回区域用户名属性。

    ```html
     areaObject.username
    ```

*   它用于设置区域用户名属性。

    ```html
    areaObject.username = username
    ```

**属性值:**它包含单值用户名，指定网址的用户名部分。

**返回值:**返回一个字符串值，代表网址的用户名部分。

**示例 1:** 本示例返回区域用户名属性。

```html
<!DOCTYPE html> 
<html> 
<title> 
    HTML DOM Area username Property 
</title> 

<body> 
    <h4> HTML DOM Area username Property </h4> 
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

        // Return username property. 
            var x = document.getElementById("Geeks").username; 
        document.getElementById("GEEK!").innerHTML = x; 
        } 
    </script> 
</body> 

</html>                    
```

**输出:**
点击按钮前:
![](img/08442eef131ed9937944ae1c5ec86153.png)

点击按钮后:
![](img/953e7a994c452d4bb3aad3875f34c2e9.png)
 **示例 2:** 本示例设置区域用户名属性。

```html
<!DOCTYPE html> 
<html> 
<title> 
    HTML DOM Area username Property 
</title> 

<body> 
    <h4> HTML DOM Area username Property </h4> 
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

        // Set username property. 
            var x = document.getElementById("Geeks").username = "abcxyz"; 
        document.getElementById("GEEK!").innerHTML = 
                "The username has been changed to " + x; 
        } 
    </script> 
</body> 

</html>                     
```

**输出:**
点击按钮前:
![](img/08442eef131ed9937944ae1c5ec86153.png)

点击按钮后:
![](img/ffcd47609d33124d23a10dfa6b0c21e4.png)

**支持的浏览器:**

*   谷歌 Chrome
*   火狐浏览器
*   歌剧