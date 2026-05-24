# HTML | DOM 区域原点属性

> 原文:[https://www . geesforgeks . org/html-DOM-area-origin-property/](https://www.geeksforgeeks.org/html-dom-area-origin-property/)

HTML 中的 DOM 区域源属性用于返回一个 URL 的协议、主机名和端口号。这是只读属性。

**语法:**

```html
 areaObject.origin
```

**返回值:**该方法返回一个 String 值，代表协议、域名(或 IP 地址)和端口号。具有“文件://”协议的 URL 可能会根据浏览器返回不同的值。

**示例:**本示例返回区域原点属性。

```html
<!DOCTYPE html> 
<html> 
<title> 
    HTML DOM Area origin Property 
</title> 

<body> 
    <h4> HTML DOM Area origin Property </h4> 
    <button onclick="GFG()">Click Here! 
    </button> 
    <map name="Geeks1"> 
        <area id="Geeks"
            shape="rect"
            coords="0, 0, 110, 100"
            alt="Geeks"
            href= 
        https://manaschhabra:manaschhabra499@www.geeksforgeeks.org/
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

        // Return origin property. 
            var x = document.getElementById("Geeks").origin; 
        document.getElementById("GEEK!").innerHTML = x; 
        } 
    </script> 
</body> 

</html>                    
```

**输出:**
点击按钮前:
![](img/2dee580b55bfcfbe14fb67b7d408efef.png)

点击按钮后:
![](img/b55a347e310ea003e2ae913e0e365275.png)

**支持的浏览器:**

*   谷歌 Chrome
*   火狐浏览器
*   歌剧
*   旅行队