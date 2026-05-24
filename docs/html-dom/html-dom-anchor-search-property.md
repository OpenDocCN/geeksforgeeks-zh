# HTML | DOM 锚点搜索属性

> 原文:[https://www . geesforgeks . org/html-DOM-anchor-search-property/](https://www.geeksforgeeks.org/html-dom-anchor-search-property/)

HTML DOM 中的**锚点搜索属性**用于设置或返回 **href 属性的查询部分。**问号(？)中。它通常用于参数传递。

**语法:**

*   它返回锚搜索属性。

    ```html
    anchorObject.search
    ```

*   它用于设置锚点搜索属性。

    ```html
    anchorObject.search = querystring 
    ```

**属性值:**包含单值**查询字符串**，用于指定网址的搜索部分。

**返回值:**它返回一个字符串值，该值代表也包含问号的网址的查询字符串部分。(?)

**示例 1:** 本示例返回锚点搜索属性。

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        HTML DOM Anchor search Property 
    </title> 
</head> 

<body> 
    <center> 
        <h1>GeeksForGeeks</h1> 

        <h2>DOM Anchor search Property</h2> 

        <p>Welcome to 
            <a href = 
"https://contribute.geeksforgeeks.org/wp-admin/post.php?post=964437&action=edit"
            id="GFG" target= "_self"> 
                GeeksforGeeks 
            </a> 
        </p> 

        <button onclick = "myGeeks()">Submit</button> 

        <p id = "sudo" style="color:green;font-size:25px;"></p> 

        <!-- Script to return Anchor search Property -->
        <script> 
            function myGeeks() { 
                var x = document.getElementById("GFG").search; 
                document.getElementById("sudo").innerHTML = x; 
            } 
        </script>
    </center> 
</body> 

</html>            
```

**输出:**
**点击按钮前:**
![](img/79ad75554276b7ea0a62dff708323ed4.png)
**点击按钮后:**
![](img/ed15b406ed553296555b510e2ab4a4e2.png)

**示例 2:** 本示例设置锚点搜索属性。

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        HTML DOM Anchor search Property 
    </title> 
</head> 

<body> 
    <center> 
        <h1>GeeksForGeeks</h1> 

        <h2>DOM Anchor search Property</h2> 

        <p>Welcome to 
            <a href = 
"https://contribute.geeksforgeeks.org/wp-admin/post.php?post=964437&action=edit"
            id="GFG" target= "_self"> 
                GeeksforGeeks 
            </a> 
        </p> 

        <button onclick = "myGeeks()">Submit</button> 

        <p id = "sudo" style="color:green;font-size:25px;"></p> 

        <!-- Script to set Anchor search Property -->
        <script> 
            function myGeeks() { 
                var x = document.getElementById("GFG").search
                    = "The value of search is changed now!"; 
                document.getElementById("sudo").innerHTML = x; 
            } 
        </script>
    </center> 
</body> 

</html>                                      
```

**输出:**
**点击按钮前:**
![](img/79ad75554276b7ea0a62dff708323ed4.png)
**点击按钮后:**
![](img/b4aecd5376242a420d787f06d3d3c655.png)

**支持的浏览器:****DOM Anchor 搜索属性**支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队