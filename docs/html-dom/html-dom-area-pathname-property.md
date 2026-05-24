# HTML | DOM 区域路径名属性

> 原文:[https://www . geesforgeks . org/html-DOM-area-pathname-property/](https://www.geeksforgeeks.org/html-dom-area-pathname-property/)

HTML DOM 中的区域路径名属性用于设置或返回 href 属性的路径名。它用于指定区域中链接的目的地。
**语法:**

*   它返回区域路径名属性。

    ```html
     areaObject.pathname
    ```

*   它用于设置区域路径名属性。

    ```html
    areaObject.pathname = path 
    ```

**属性值:**它包含单个值**路径**，指定网址的路径名。

**返回值:**返回一个代表网址路径名的字符串值。

**示例 1:** 本示例返回区域路径名属性。

```html
<!DOCTYPE html> 
<html> 
<title> 
    HTML DOM Area pathname Property 
</title> 

<body> 
    <h4> HTML DOM Area pathname Property </h4> 
    <button onclick="GFG()">Click Here! 
    </button> 
    <map name="Geeks1"> 
        <area id="Geeks"
            shape="rect"
            coords="0, 0, 110, 100"
            alt="Geeks"
            href= 
        https://manaschhabra:manaschhabra499@www.geeksforgeeks.org/abc.html
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

        // Return pathname property. 
            var x = document.getElementById("Geeks").pathname; 
        document.getElementById("GEEK!").innerHTML = x; 
        } 
    </script> 
</body> 

</html>                    
```

**输出:**
点击按钮前:
![](img/eda877087c02bde00cbef6526256c91c.png)

点击按钮后:
![](img/3879a761dd38d1b0aafedb7d96ad368d.png)
 **示例 2:** 本示例设置区域路径名属性。

```html
<!DOCTYPE html> 
<html> 
<title> 
    HTML DOM Area pathname Property 
</title> 

<body> 
    <h4> HTML DOM Area pathname Property </h4> 
    <button onclick="GFG()">Click Here! 
    </button> 
    <map name="Geeks1"> 
        <area id="Geeks"
            shape="rect"
            coords="0, 0, 110, 100"
            alt="Geeks"
            href= 
        https://manaschhabra:manaschhabra499@www.geeksforgeeks.org/abc.html
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

        // Set pathname property. 
            var x = document.getElementById("Geeks").pathname = "xyz"; 
        document.getElementById("GEEK!").innerHTML = 
                "The pathname has been changed to " + x; 
        } 
    </script> 
</body> 

</html>                     
```

**输出:**
点击按钮前:
![](img/eda877087c02bde00cbef6526256c91c.png)

点击按钮后:
![](img/63c9e712b63887ebf9f1be119be6642f.png)
**支持的浏览器:**

*   谷歌 Chrome
*   火狐浏览器
*   微软公司出品的 web 浏览器
*   歌剧
*   旅行队