# HTML | DOM 区域坐标属性

> 原文:[https://www . geesforgeks . org/html-DOM-area-coords-property/](https://www.geeksforgeeks.org/html-dom-area-coords-property/)

HTML DOM 中的区域坐标属性用于设置或返回区域坐标属性的值。它指定了一个区域的 x 和 y 坐标。

**语法:**

*   它返回区域坐标属性。

    ```html
     areaObject.coords
    ```

*   它用于设置区域坐标属性。

    ```html
    areaObject.coords = value
    ```

**属性值:**

*   **x1，y1，x2，y2:** 指定矩形左上角(x1，y1)和右下角(x2，y2)的坐标。
*   **x，y，半径:**指定圆的中心坐标(x，y)和半径(半径)。
*   **x1，y1，x2，y2，..，xn，yn:** 指定多边形的坐标。如果第一个和最后一个坐标对不相同，浏览器将添加最后一个坐标对来闭合多边形。

**返回值:**返回一个字符串值，代表逗号分隔的坐标列表。

**示例 1:** 本示例返回面积坐标属性。

```html
<!DOCTYPE html> 
<html> 
<title> 
    HTML DOM Area coords Property 
</title> 

<body> 
    <h4> HTML DOM Area coords Property </h4> 
    <button onclick="GFG()">Click Here! 
    </button> 
    <map name="Geeks1"> 
        <area id="Geeks"
            shape="rect"
            coords="0, 0, 110, 100"
            alt="Geeks"
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

        // Return coords property. 
            var x = document.getElementById("Geeks").coords; 
        document.getElementById("GEEK!").innerHTML = x; 
        } 
    </script> 
</body> 

</html>                    
```

**输出:**
点击按钮前:
![](img/84b55afae865aa6d3a43dd285f006006.png)

点击按钮后:
![](img/41fb4e145e43a38764953ddf7952b4c8.png)
 **示例 2:** 本示例设置区域坐标属性。

```html
<!DOCTYPE html> 
<html> 
<title> 
    HTML DOM Area coords Property 
</title> 

<body> 
    <h4> HTML DOM Area coords Property </h4> 
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

        // Sets coords property. 
            var x = document.getElementById("Geeks").coords = 
                "2, 2, 100, 100"; 
        document.getElementById("GEEK!").innerHTML = 
                "The coords has been changed to " + x; 
        } 
    </script> 
</body> 

</html>                     
```

**输出:**
点击按钮前:
![](img/84b55afae865aa6d3a43dd285f006006.png)

点击按钮后:
![](img/ba6e551e03f8699181ac9b4036a68ecb.png)

**支持的浏览器:**

*   谷歌 Chrome
*   火狐浏览器
*   微软公司出品的 web 浏览器
*   歌剧
*   旅行队