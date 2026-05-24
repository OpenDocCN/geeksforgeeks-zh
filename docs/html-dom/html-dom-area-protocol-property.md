# HTML | DOM 区域协议属性

> 原文:[https://www . geesforgeks . org/html-DOM-area-protocol-property/](https://www.geeksforgeeks.org/html-dom-area-protocol-property/)

HTML 中的 Area 协议属性用于返回协议或设置当前 URL 的协议。它返回一个字符串，该字符串包含当前 URL 的协议部分，包括冒号(:)。
**语法:**

*   它返回区域协议属性。

    ```html
     areaObject.protocol
    ```

*   它用于设置区域协议属性。

    ```html
    areaObject.protocol = protocol 
    ```

**属性值:**该方法接受字符串类型的单值**协议**。用于设置 URL 的协议。协议的可能值是- file:，ftp:，http:，https:等。

**返回值:**返回包含当前网址协议部分的字符串，包括冒号(:)。

**示例 1:** 本示例返回区域协议属性。

```html
<!DOCTYPE html> 
<html> 
<title> 
    HTML DOM Area protocol Property 
</title> 

<body> 
    <h4> HTML DOM Area protocol Property </h4> 
    <button onclick="GFG()">Click Here! 
    </button> 
    <map name="Geeks1"> 
        <area id="Geeks"
            shape="rect"
            coords="0, 0, 110, 100"
            alt="Geeks"
            href= 
        https://manaschhabra:manaschhabra499@www.geeksforgeeks.org:80/
                        target="_self"
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

        // Return protocol property. 
            var x = document.getElementById("Geeks").protocol; 
        document.getElementById("GEEK!").innerHTML = x; 
        } 
    </script> 
</body> 

</html>                    
```

**输出:**
点击按钮前:
![](img/f5544ae43eea4f41c83c6d4121d5d8e6.png)

点击按钮后:
![](img/fab4aba099c1c93452ccd0aea3148f0f.png)

 **示例 2:** 本示例设置区域协议属性。

```html
<!DOCTYPE html> 
<html> 
<title> 
    HTML DOM Area protocol Property 
</title> 

<body> 
    <h4> HTML DOM Area protocol Property </h4> 
    <button onclick="GFG()">Click Here! 
    </button> 
    <map name="Geeks1"> 
        <area id="Geeks"
            shape="rect"
            coords="0, 0, 110, 100"
            alt="Geeks"
            href= 
        https://manaschhabra:manaschhabra499@www.geeksforgeeks.org:80/
                       target="_self"
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

        // Set protocol property. 
            var x = document.getElementById("Geeks").protocol = "ftp:"; 
        document.getElementById("GEEK!").innerHTML = 
                "The protocol has been changed to " + x; 
        } 
    </script> 
</body> 

</html>                     
```

**输出:**
点击按钮前:
![](img/f5544ae43eea4f41c83c6d4121d5d8e6.png)

点击按钮后:
![](img/287c6ecb8950b0194b1104c61a9afec8.png)

**支持的浏览器:**

*   谷歌 Chrome
*   火狐浏览器
*   微软公司出品的 web 浏览器
*   歌剧
*   旅行队