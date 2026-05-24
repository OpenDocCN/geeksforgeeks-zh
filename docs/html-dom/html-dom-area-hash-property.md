# HTML | DOM 区域哈希属性

> 原文:[https://www.geeksforgeeks.org/html-dom-area-hash-property/](https://www.geeksforgeeks.org/html-dom-area-hash-property/)

HTML DOM 中的 DOM 区域哈希属性用于设置或返回 href 属性值的锚点部分。锚点部分是网址中散列符号(#)之后的部分。

**语法:**

*   它返回区域散列属性。

    ```html
     areaObject.hash
    ```

*   它用于设置区域哈希属性。

    ```html
    areaObject.hash = anchorname 
    ```

**属性值:**包含单个值**锚点名称**，指定网址的锚点部分。

**返回值:**它返回一个字符串值，该值代表包含哈希符号(#)的网址的锚部分。

**示例 1:** 本示例返回区域哈希属性。

```html
<!DOCTYPE html> 
<html> 
<title> 
    HTML DOM Area hash Property 
</title> 

<body> 
    <h4> HTML DOM Area hash Property </h4> 
    <button onclick="GFG()">Click Here! 
    </button> 
    <map name="Geeks1"> 
        <area id="Geeks"
            shape="rect"
            coords="0, 0, 110, 100"
            alt="Geeks"
            href= 
        https://manaschhabra:manaschhabra499@www.geeksforgeeks.org#abc/
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

        // Return hash property. 
            var x = document.getElementById("Geeks").hash; 
        document.getElementById("GEEK!").innerHTML = x; 
        } 
    </script> 
</body> 

</html>                    
```

**输出:**
点击按钮前:
![](img/16947349ba5efe24a0301c1714415aa6.png)

点击按钮后:
![](img/aa8b2c5396a5c70d4e3e1352fbc10b6d.png)

 **示例 2:** 本示例设置区域哈希属性。

```html
<!DOCTYPE html> 
<html> 
<title> 
    HTML DOM Area hash Property 
</title> 

<body> 
    <h4> HTML DOM Area hash Property </h4> 
    <button onclick="GFG()">Click Here! 
    </button> 
    <map name="Geeks1"> 
        <area id="Geeks"
            shape="rect"
            coords="0, 0, 110, 100"
            alt="Geeks"
            href= 
        https://manaschhabra:manaschhabra499@www.geeksforgeeks.org#abc/
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

        // Set hash property. 
            var x = document.getElementById("Geeks").hash = "xyz"; 
        document.getElementById("GEEK!").innerHTML = 
                "The hash value has been changed to " + x; 
        } 
    </script> 
</body> 

</html>                     
```

**输出:**
点击按钮前:
![](img/16947349ba5efe24a0301c1714415aa6.png)

点击按钮后:
![](img/7bf797ddc072002ee545cb7bc4ed2642.png)
**支持的浏览器:**

*   谷歌 Chrome
*   火狐浏览器
*   微软公司出品的 web 浏览器
*   歌剧
*   旅行队