# HTML | DOM 区域搜索属性

> 原文:[https://www . geesforgeks . org/html-DOM-area-search-property/](https://www.geeksforgeeks.org/html-dom-area-search-property/)

HTML DOM 中的区域搜索属性用于设置或返回 href 属性的查询字符串部分。它是网址中问号之后的部分。
**语法:**

*   它返回区域搜索属性。

    ```html
     areaObject.search
    ```

*   它用于设置区域搜索属性。

    ```html
    areaObject.search = querystring 
    ```

**属性值:**包含单个值**查询**，指定网址的搜索部分。

**返回值:**返回一个字符串值，代表网址的查询字符串，包括(？)问号。

**示例 1:** 本示例返回区域搜索属性。

```html
<!DOCTYPE html> 
<html> 
<title> 
    HTML DOM Area search Property 
</title> 

<body> 
    <h4> HTML DOM Area search Property </h4> 
    <button onclick="GFG()">Click Here! 
    </button> 
    <map name="Geeks1"> 
        <area id="Geeks"
            shape="rect"
            coords="0, 0, 110, 100"
            alt="Geeks"
            href= 
     https://manaschhabra:manaschhabra499@www.geeksforgeeks.org?id=Geeks/
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

        // Return search property. 
            var x = document.getElementById("Geeks").search; 
        document.getElementById("GEEK!").innerHTML = x; 
        } 
    </script> 
</body> 

</html>                    
```

**输出:**
点击按钮前:
![](img/4991d712264b8b1c78b8552edf4bc8eb.png)

点击按钮后:
![](img/53110f77681c02004ba1e957b840334b.png)

 **示例 2:** 本示例设置区域搜索属性。

```html
<!DOCTYPE html> 
<html> 
<title> 
    HTML DOM Area search Property 
</title> 

<body> 
    <h4> HTML DOM Area search Property </h4> 
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

        // Set search property. 
            var x = document.getElementById("Geeks").search = "abc"; 
        document.getElementById("GEEK!").innerHTML = 
                "The querystring has been changed to " + x; 
        } 
    </script> 
</body> 

</html>                     
```

**输出:**
点击按钮前:
![](img/4991d712264b8b1c78b8552edf4bc8eb.png)

点击按钮后:
![](img/947d93e53c26219f5ba0142b09019dad.png)

**支持的浏览器:**

*   谷歌 Chrome
*   火狐浏览器
*   微软公司出品的 web 浏览器
*   歌剧
*   旅行队