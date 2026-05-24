# HTML | DOM 区域 alt 属性

> 原文:[https://www.geeksforgeeks.org/html-dom-area-alt-property/](https://www.geeksforgeeks.org/html-dom-area-alt-property/)

HTML DOM 中的区域 alt 属性用于设置或返回 alt 属性的值。如果图像不可见，它用于指定区域的替代名称。

**语法:**

*   它返回面积替代属性。

    ```html
     areaObject.alt
    ```

*   它用于设置区域替代属性。

    ```html
    areaObject.alt = text
    ```

**属性值:**它包含指定区域替代文本的单个值。

**返回值:**返回一个字符串值，代表该区域的替换文本。

**示例 1:** 本示例返回面积替代属性。

```html
<!DOCTYPE html> 
<html> 
<title> 
    HTML DOM Area alt Property 
</title> 

<body> 
    <h4> HTML DOM Area alt Property </h4> 
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

        // Return alt property 
            var x = document.getElementById("Geeks").alt; 
        document.getElementById("GEEK!").innerHTML = x; 
        } 
    </script> 
</body> 

</html>                    
```

**输出:**
点击按钮前:
![](img/65412f1b0c47730a215616a6a40a358d.png)

点击按钮后:
![](img/777e4de0dcbe90ccc972491a88a87e3f.png)
 **示例 2:** 本示例设置区域 alt 属性。

```html
<!DOCTYPE html> 
<html> 
<title> 
    HTML DOM Area alt Property 
</title> 

<body> 
    <h4> HTML DOM Area alt Property </h4> 
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

        // Sets alt property. 
            var x = document.getElementById("Geeks").alt = "abcxyz"; 
        document.getElementById("GEEK!").innerHTML = 
                "The alt value has been changed to " + x; 
        } 
    </script> 
</body> 

</html>                     
```

**输出:**
点击按钮前:
![](img/65412f1b0c47730a215616a6a40a358d.png)

点击按钮后:
![](img/c879ac15f117de1fc70837064ac86daf.png)

**支持的浏览器:**

*   谷歌 Chrome
*   火狐浏览器
*   微软公司出品的 web 浏览器
*   歌剧
*   旅行队