# HTML | DOM 区域主机属性

> 原文:[https://www.geeksforgeeks.org/html-dom-area-host-property/](https://www.geeksforgeeks.org/html-dom-area-host-property/)

HTML DOM 中的 DOM 区域宿主属性用于设置或返回 href 属性值的主机名和端口部分。
**语法:**

*   它返回区域宿主属性。

    ```html
     areaObject.host
    ```

*   它用于设置区域主体属性。

    ```html
    areaObject.host = hostname:port 
    ```

**属性值:**包含单个值**主机名:端口**，指定网址的主机名和端口号。

**返回值:**返回一个字符串值，代表网址的域名和端口号。

**示例 1:** 本示例返回区域主机属性。

```html
<!DOCTYPE html> 
<html> 
<title> 
    HTML DOM Area host Property 
</title> 

<body> 
    <h4> HTML DOM Area host Property </h4> 
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

        // Return host property. 
            var x = document.getElementById("Geeks").host; 
        document.getElementById("GEEK!").innerHTML = x; 
        } 
    </script> 
</body> 

</html>                    
```

**输出:**
点击按钮前:
![](img/39bb591822a59b180d81475472cbb132.png)

点击按钮后:
![](img/327bf6ab631b26e47d02503e126e3baf.png)

 **示例 2:** 本示例设置 Area 宿主属性。

```html
<!DOCTYPE html> 
<html> 
<title> 
    HTML DOM Area host Property 
</title> 

<body> 
    <h4> HTML DOM Area host Property </h4> 
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

        // Set host property. 
            var x = document.getElementById("Geeks").host = 
             "www.geeksforgeeks.org:111"; 
        document.getElementById("GEEK!").innerHTML = 
                "The host has been changed to " + x; 
        } 
    </script> 
</body> 

</html>                     
```

**输出:**
点击按钮前:
![](img/39bb591822a59b180d81475472cbb132.png)

点击按钮后:
![](img/5e377d58c05b46f7461d751276ba0d72.png)

**支持的浏览器:**

*   谷歌 Chrome
*   火狐浏览器
*   微软公司出品的 web 浏览器
*   歌剧
*   旅行队