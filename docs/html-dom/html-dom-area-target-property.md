# HTML | DOM 区域目标属性

> 原文:[https://www . geesforgeks . org/html-DOM-area-target-property/](https://www.geeksforgeeks.org/html-dom-area-target-property/)

HTML DOM 中的区域目标属性用于设置或返回目标属性的值。它用于指定链接文档应该打开的位置。

**语法:**

*   它返回区域目标属性。

    ```html
     areaObject.target
    ```

*   它用于设置区域目标属性。

    ```html
    areaObject.target = _blank|_self|_parent|_top|framename 
    ```

**属性值:**它包含指定形状类型的单值形状。

*   **_blank:** 在新窗口打开链接。
*   **_self:** 在同一框架中打开链接的文档。
*   **_parent:** 打开父框架集中的链接文档。
*   **_top:** 在窗口的整个正文中打开链接的文档。
*   **框架名称:**在命名框架中打开链接文档。

**返回值:**返回一个字符串值，代表打开链接文档的位置。

**示例 1:** 本示例返回面积目标属性。

```html
<!DOCTYPE html> 
<html> 
<title> 
    HTML DOM Area target Property 
</title> 

<body> 
    <h4> HTML DOM Area target Property </h4> 
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

        // Return target property. 
            var x = document.getElementById("Geeks").target; 
        document.getElementById("GEEK!").innerHTML = x; 
        } 
    </script> 
</body> 

</html>                    
```

**输出:**
点击按钮前:
![](img/e6503be56f94de134b5eedf3edce4260.png)

点击按钮后:
![](img/a9ce158931ad78f82fc54708d1d44b5a.png)
 **示例 2:** 本示例设置区域目标属性。

```html
<!DOCTYPE html> 
<html> 
<title> 
    HTML DOM Area target Property 
</title> 

<body> 
    <h4> HTML DOM Area target Property </h4> 
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

        // Set target property. 
            var x = document.getElementById("Geeks").target = "_blank"; 
        document.getElementById("GEEK!").innerHTML = 
                "The value of target attribute has been changed to " + x; 
        } 
    </script> 
</body> 

</html>                     
```

**输出:**
点击按钮前:
![](img/e6503be56f94de134b5eedf3edce4260.png)

点击按钮后:
![](img/4c963c959e524e2f33bbddc97315eb8b.png)

**支持的浏览器:**

*   谷歌 Chrome
*   火狐浏览器
*   微软公司出品的 web 浏览器
*   歌剧
*   旅行队