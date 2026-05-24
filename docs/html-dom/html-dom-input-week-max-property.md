# HTML | DOM 输入周最大属性

> 原文:[https://www . geesforgeks . org/html-DOM-input-week-max-property/](https://www.geeksforgeeks.org/html-dom-input-week-max-property/)

HTML DOM 中的 **DOM 输入周最大值**属性用于设置或返回周字段的最大属性值。max 属性指定周字段的最大值(周和年)。

**语法:**

*   它返回 max 属性。

    ```html
    weekObject.max
    ```

*   它用于设置 max 属性。

    ```html
    weekObject.max = YYYY-WWW
    ```

**属性值:**

*   **YYYY-WWW:** 该值表示最大年份和星期。这里 YYYY 是年份即 2019 年，WWW 是起始字母 W 即 W32 的一周。

**返回值:**返回一个字符串，代表一周字段允许的最大值。

**示例-1:** 本示例返回输入周最大值属性。

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        HTML DOM Input Week max Property
    </title> 
</head> 

<body style="text-align:center;"> 

    <h1>GeeksForGeeks</h1> 

    <h2>DOM Input Week max Property</h2> 
            <form id="myGeeks">
    <input type="week" id="week_id" name="geeks" max="2019-W12"> 
                 </form>
                 <br>
    <button onclick="myGeeks()">Click Here!</button> 

    <p id="GFG" style="font-size:20px;"></p> 

    <!-- Script to return the max property-->
    <script> 
        function myGeeks() { 
            var gfg = document.getElementById("week_id").max;
            document.getElementById("GFG").innerHTML = gfg;
        } 
    </script> 
</body> 

</html>                     
```

**输出**
**点击按钮前:**
![](img/d04a7234e0b363757cf6e944ea3f2a38.png)

**点击按钮后:**
![](img/9467ffa2c61d22ee1cc3a9f187fdf7c1.png)
**示例-2:** 本示例说明如何**设置**属性。

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        HTML DOM Input Week max Property
    </title> 
</head> 

<body style="text-align:center;"> 

    <h1>GeeksForGeeks</h1> 

    <h2>DOM Input Week max Property</h2> 
            <form id="myGeeks">
    <input type="week" id="week_id" name="geeks"> 
                </form>
                <br>
    <button onclick="myGeeks()">Click Here!</button> 

    <p id="GFG" style="font-size:20px;"></p> 

    <!-- Script to set the max property-->
    <script> 
        function myGeeks() { 
            var gfg = document.getElementById("week_id");
            gfg.max = "2019-W13";
            var g =    gfg.max;        
            document.getElementById("GFG").innerHTML = g;
        } 
    </script> 
</body> 

</html>                    
```

**输出:**
**点击按钮前:**
![](img/d04a7234e0b363757cf6e944ea3f2a38.png)

**点击按钮后:**
![](img/b02c62ceb583eb58f05ad2d2fa20ea2a.png)

**支持的浏览器:**T2 DOM 输入周最大属性支持的浏览器如下:

*   谷歌 Chrome
*   Internet Explorer 10.0 +
*   火狐浏览器
*   歌剧
*   旅行队

**注意:**在 Firefox 中，输入 type="week "元素不显示任何日期字段或日历。