# HTML | DOM 输入月最大属性

> 原文:[https://www . geesforgeks . org/html-DOM-input-month-max-property/](https://www.geeksforgeeks.org/html-dom-input-month-max-property/)

HTML DOM 中的 **DOM 输入月最大值**属性用于设置或返回月字段的最大属性值。max 属性指定“月”字段的最大值(月和年)。

**语法:**

*   它返回 max 属性。

    ```html
    monthObject.max
    ```

*   它用于设置 max 属性。

    ```html
    monthObject.max = YYYY-MM
    ```

**属性值:**

*   **YYYY-WWW:** 该值表示最大年份和月份。这里 YYYY 是年份即 2019，MM 是月份即 02。

**返回值:**返回一个字符串，代表月字段允许的最大值。

**示例-1:** 本示例返回输入月最大值属性。

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        HTML DOM Input Month max Property
    </title> 
</head> 

<body style="text-align:center;"> 

    <h1>GeeksForGeeks</h1> 

    <h2>DOM Input Month max Property</h2> 
            <form id="myGeeks">
    <input type="month" id="month_id" name="geeks" max="2019-12"> 
                 </form>
                 <br>
    <button onclick="myGeeks()">Click Here!</button> 

    <p id="GFG" style="font-size:20px;"></p> 

    <!-- Script to return the max property-->
    <script> 
        function myGeeks() { 
            var gfg = document.getElementById("month_id").max;
            document.getElementById("GFG").innerHTML = gfg;
        } 
    </script> 
</body> 

</html>                     
```

**输出**
**点击按钮前:**
![](img/1db69ea868d1eee254fb1510b08c3a22.png)

**点击按钮后:**
![](img/e37eee2651f4c6f47c93d843935bdaee.png)
**示例-2:** 本示例说明如何**设置**属性。

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        HTML DOM Input Month max Property
    </title> 
</head> 

<body style="text-align:center;"> 

    <h1>GeeksForGeeks</h1> 

    <h2>DOM Input Month max Property</h2> 
            <form id="myGeeks">
    <input type="month" id="month_id" name="geeks"> 
                </form>
                <br>
    <button onclick="myGeeks()">Click Here!</button> 

    <p id="GFG" style="font-size:20px;"></p> 

    <!-- Script to set the max property-->
    <script> 
        function myGeeks() { 
            var gfg = document.getElementById("month_id");
            gfg.max = "2019-01";
            var g =    gfg.max;        
            document.getElementById("GFG").innerHTML = g;
        } 
    </script> 
</body> 

</html>                    
```

**输出:**
**点击按钮前:**
![](img/1db69ea868d1eee254fb1510b08c3a22.png)

**点击按钮后:**
![](img/547845ec432a62a1902d901959fac2c9.png)

**支持的浏览器:**T2 DOM 输入月最大属性支持的浏览器如下:

*   谷歌 Chrome
*   Internet Explorer 10.0 +
*   火狐浏览器
*   歌剧
*   旅行队

**注意:**在 Firefox 中，输入 type="month "元素不显示任何日期字段或日历。