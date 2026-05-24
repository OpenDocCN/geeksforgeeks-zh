# HTML | DOM 输入周最小属性

> 原文:[https://www . geesforgeks . org/html-DOM-input-week-min-property/](https://www.geeksforgeeks.org/html-dom-input-week-min-property/)

HTML DOM 中的 **DOM 输入周最小值**属性用于设置或返回周字段的最小值属性的值。min 属性指定周字段的最小值(周和年)。

**语法:**

*   它返回 min 属性。

    ```html
    weekObject.min
    ```

*   它用于设置 min 属性。

    ```html
    weekObject.min = YYYY-WWW
    ```

**属性值:**

*   **YYYY-WWW:** 该值表示最小的年份和星期。这里 YYYY 是年份即 2019 年，WWW 是起始字母 W 即 W32 的一周。

**返回值:**返回一个字符串，代表一周字段允许的最小值。

**示例-1:** 本示例返回输入周最小值属性。

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        HTML DOM Input Week min Property
    </title> 
</head> 

<body style="text-align:center;"> 

    <h1>GeeksForGeeks</h1> 

    <h2>DOM Input Week min Property</h2> 
            <form id="myGeeks">
    <input type="week" id="week_id" name="geeks" min="2019-W12"> 
                 </form>
                 <br>
    <button onclick="myGeeks()">Click Here!</button> 

    <p id="GFG" style="font-size:20px;"></p> 

    <!-- Script to return the min property-->
    <script> 
        function myGeeks() { 
            var gfg = document.getElementById("week_id").min;
            document.getElementById("GFG").innerHTML = gfg;
        } 
    </script> 
</body> 

</html>                     
```

**输出**
**点击按钮前:**
![](img/fee92182b7f352077ed6e0fc3e757e5f.png)

**点击按钮后:**
![](img/cec96c35f937611b6c5fb922ae205951.png)
**示例-2:** 本示例说明如何**设置**属性。

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        HTML DOM Input Week min Property
    </title> 
</head> 

<body style="text-align:center;"> 

    <h1>GeeksForGeeks</h1> 

    <h2>DOM Input Week min Property</h2> 
            <form id="myGeeks">
    <input type="week" id="week_id" name="geeks" > 
                </form>
                <br>
    <button onclick="myGeeks()">Click Here!</button> 

    <p id="GFG" style="font-size:20px;"></p> 

    <!-- Script to set the min property-->
    <script> 
        function myGeeks() { 
            var gfg = document.getElementById("week_id");
            gfg.min = "2019-W13";
            var g =    gfg.min;        
            document.getElementById("GFG").innerHTML = g;
        } 
    </script> 
</body> 

</html>                    
```

**输出:**
**点击按钮前:**
![](img/fee92182b7f352077ed6e0fc3e757e5f.png)
**点击按钮后:**
![](img/15c9be99cb17498a50806609b3a5ffbd.png)

**支持的浏览器:**T2 DOM 输入周最小属性支持的浏览器如下:

*   谷歌 Chrome
*   Internet Explorer 10.0 +
*   火狐浏览器
*   歌剧
*   旅行队

**注意:**在 Firefox 中，输入 type="week "元素不显示任何日期字段或日历。