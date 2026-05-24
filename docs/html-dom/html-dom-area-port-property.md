# HTML | DOM 区域端口属性

> 原文:[https://www.geeksforgeeks.org/html-dom-area-port-property/](https://www.geeksforgeeks.org/html-dom-area-port-property/)

HTML DOM 中的区域端口属性用于设置或返回 href 属性的端口部分。它被用来，即 href 指定一个区域中链接的目的地。
**语法:**

*   它返回区域端口属性。

    ```html
     areaObject.port
    ```

*   它用于设置区域端口属性。

    ```html
    areaObject.port = port 
    ```

**属性值:**包含单个值**端口**，指定网址的端口号。

**返回值:**返回一个代表网址端口号的字符串值。

**示例 1:** 本示例返回区域路径名属性。

```html
<!DOCTYPE html> 
<html> 
<title> 
    HTML DOM Area port Property 
</title> 

<body> 
    <h4> HTML DOM Area port Property </h4> 
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

        // Return port property. 
            var x = document.getElementById("Geeks").port; 
        document.getElementById("GEEK!").innerHTML = x; 
        } 
    </script> 
</body> 

</html>                    
```

**输出:**
点击按钮前:
![](img/40fc61928220f5bc3c9af578e4f488fe.png)

点击按钮后:
![](img/d8f2b2df84ecbfff9d67c5ce214f74c9.png)

 **示例 2:** 本示例设置区域端口属性。

```html
<!DOCTYPE html> 
<html> 
<title> 
    HTML DOM Area port Property 
</title> 

<body> 
    <h4> HTML DOM Area port Property </h4> 
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

        // Set port property. 
            var x = document.getElementById("Geeks").port = "111"; 
        document.getElementById("GEEK!").innerHTML = 
                "The port number has been changed to " + x; 
        } 
    </script> 
</body> 

</html>                     
```

**输出:**
点击按钮前:
![](img/40fc61928220f5bc3c9af578e4f488fe.png)

点击按钮后:
![](img/369dbdbd3b5b132eb4a2aba745859489.png)
**支持的浏览器:**

*   谷歌 Chrome
*   火狐浏览器
*   微软公司出品的 web 浏览器
*   歌剧
*   旅行队