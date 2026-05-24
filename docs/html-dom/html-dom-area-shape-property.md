# HTML | DOM 区域形状属性

> 原文:[https://www.geeksforgeeks.org/html-dom-area-shape-property/](https://www.geeksforgeeks.org/html-dom-area-shape-property/)

“区域”形状属性用于设置或返回形状属性的值。它用于定义区域的形状。它与 coords 属性一起用于定义形状、大小等。

**语法:**

*   它返回区域形状属性。

    ```html
     areaObject.shape
    ```

*   它用于设置“面积”形状属性。

    ```html
    areaObject.shape = default|rect|circle|poly 
    ```

**属性值:**它包含指定形状类型的单值形状。

*   **默认:**用于指定整个区域。
*   **矩形:**用于指定矩形区域。
*   **圆形:**用于指定圆形区域。
*   **多边形:**用于指定多边形区域。

**返回值:**返回代表区域形状的字符串值。

**示例 1:** 本示例返回区域形状属性。

```html
<!DOCTYPE html> 
<html> 
<title> 
    HTML DOM Area shape Property 
</title> 

<body> 
    <h4> HTML DOM Area shape Property </h4> 
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

        // Return shape property. 
            var x = document.getElementById("Geeks").shape; 
        document.getElementById("GEEK!").innerHTML = x; 
        } 
    </script> 
</body> 

</html>                    
```

**输出:**
点击按钮前:
![](img/737d71317fd44c4234a18f6939b1e44b.png)

点击按钮后:
![](img/e73a993234f32bdcc39090b2bea8d1a3.png)
 **示例 2:** 本示例设置区域形状属性。

```html
<!DOCTYPE html> 
<html> 
<title> 
    HTML DOM Area shape Property 
</title> 

<body> 
    <h4> HTML DOM Area shape Property </h4> 
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

        // Set shape property. 
            var x = document.getElementById("Geeks").shape = "circle"; 
        document.getElementById("GEEK!").innerHTML = 
                "The value of shape attribute has been changed to " + x; 
        } 
    </script> 
</body> 

</html>                     
```

**输出:**
点击按钮前:
![](img/737d71317fd44c4234a18f6939b1e44b.png)

点击按钮后:
![](img/b9e8b98701ebd22aa8ee988e54ab2708.png)

**支持的浏览器:**

*   谷歌 Chrome
*   火狐浏览器
*   微软公司出品的 web 浏览器
*   歌剧
*   旅行队