# HTML | DOM 输入周值属性

> 原文:[https://www . geesforgeks . org/html-DOM-input-week-value-property/](https://www.geeksforgeeks.org/html-dom-input-week-value-property/)

**输入周值**属性用于设置或返回周字段的值属性的值。“输入周”值属性可用于为“周”字段指定周和年。

**语法:**

*   用于返回值属性:

    ```html
    weekObject.value
    ```

*   用于设置值属性:

    ```html
    weekObject.value = YYYY-WWW
    ```

**属性值:**

*   **YYYY-WWW:** 该值表示年和周。这里 YYYY 是年份即 2019 年，WWW 是起始字母 W 即 W32 的一周。

**返回值:**返回一个代表周字段值的字符串。

下面的程序说明了周值属性:
**示例-1:** 本示例返回输入周值属性。

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        HTML DOM Input Week value Property
    </title> 
</head> 

<body style="text-align:center;"> 

    <h1>GeeksForGeeks</h1> 

    <h2>DOM Input Week value Property</h2> 
            <form id="myGeeks">
    <input type="week" id="week_id" name="geeks" value="2019-W10"> 
                 </form>
                 <br>
    <button onclick="myGeeks()">Click Here!</button> 

    <p id="GFG" style="font-size:20px;"></p> 

    <!-- Script to return the value Property-->
    <script> 
        function myGeeks() { 
            var gfg = document.getElementById("week_id").value;
            document.getElementById("GFG").innerHTML = gfg;
        } 
    </script> 
</body> 

</html>                     
```

**输出**
**点击按钮前:**
![](img/d3a3ca0e511106125b59fff090c730e6.png)

**点击按钮后:**
![](img/c181cad48f136e6c6305ffce165614ad.png)

**示例-2:** 本示例说明如何**设置**属性。

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        HTML DOM Input Week value Property
    </title> 
</head> 

<body style="text-align:center;"> 

    <h1>GeeksForGeeks</h1> 

    <h2>DOM Input Week value Property</h2> 
            <form id="myGeeks">
    <input type="week" id="week_id" name="geeks" > 
                </form>
                <br>
    <button onclick="myGeeks()">Click Here!</button> 

    <p id="GFG" style="font-size:20px;"></p> 

    <!-- Script to set the value Property-->
    <script> 
        function myGeeks() { 
            var gfg = document.getElementById("week_id");
            gfg.value = "2019-W09";
            var g =    gfg.value;        
            document.getElementById("GFG").innerHTML = g;
        } 
    </script> 
</body> 

</html>                    
```

**输出:**
**点击按钮前:**
![](img/54d90093a98829babac30efd66d46b46.png)

**点击按钮后:**
![](img/4661e744c6db0cdad8fb695b820acb11.png)

**支持的浏览器:**T2 DOM 输入周值属性支持的浏览器如下:

*   谷歌 Chrome
*   Internet Explorer 10.0 +
*   火狐浏览器
*   歌剧
*   旅行队

**注意:**在 Firefox 中，输入 type="week "元素不显示任何日期字段或日历。