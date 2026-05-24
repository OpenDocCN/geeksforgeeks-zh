# HTML | DOM 输入月份名称属性

> 原文:[https://www . geesforgeks . org/html-DOM-input-month-name-property/](https://www.geeksforgeeks.org/html-dom-input-month-name-property/)

HTML DOM 中的**输入月份名称属性**用于设置或返回输入月份字段的名称属性值。每个输入月份字段都需要名称属性。如果没有在输入字段中指定 name 属性，则根本不会发送该字段的数据。

**语法:**

*   它返回输入月份名称属性。

    ```html
    monthObject.name
    ```

*   它用于设置输入月份名称属性。

    ```html
    monthObject.name = name
    ```

**属性值:**它包含一个属性值，即用于指定月份字段名称的名称。

**返回值:**返回一个代表输入月份字段名称的字符串值。

**示例-1:** 本示例返回输入月份名称属性。

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        HTML DOM Input Month name Property
    </title> 
</head> 

<body style="text-align:center;"> 

    <h1>GeeksForGeeks</h1> 

    <h2>DOM Input Month name Property</h2> 
            <form id="myGeeks">
    <input type="month" id="month_id" name="geeks"> 
                 </form>
                 <br>
    <button onclick="myGeeks()">Click Here!</button> 

    <p id="GFG" style="font-size:20px;"></p> 

    <!-- Script to return the name  Property-->
    <script> 
        function myGeeks() { 
            var gfg = document.getElementById("month_id").name ;
            document.getElementById("GFG").innerHTML = gfg;
        } 
    </script> 
</body> 

</html>                     
```

**输出**
**点击按钮前:**
![](img/8cdfb5a0d1acf885dcd1b8ca79aac71e.png)

**点击按钮后:**
![](img/b5c6e567288be828cd56f4f169215594.png)
**示例-2:** 本示例说明如何**设置**名称属性。

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        HTML DOM Input Month name Property
    </title> 
</head> 

<body style="text-align:center;"> 

    <h1>GeeksForGeeks</h1> 

    <h2>DOM Input Month name Property</h2> 
            <form id="myGeeks">
    <input type="month" id="month_id" name="geeks"> 
                </form>
                <br>
    <button onclick="myGeeks()">Click Here!</button> 

    <p id="GFG" style="font-size:20px;"></p> 

    <!-- Script to set the name Property-->
    <script> 
        function myGeeks() { 
            var gfg = document.getElementById("month_id");
            gfg.name = "geeks2";    
            document.getElementById("GFG").innerHTML = 
                        "The name of field is changed to " + gfg.name;
        } 
    </script> 
</body> 

</html>                    
```

**输出:**
**点击按钮前:**
![](img/8cdfb5a0d1acf885dcd1b8ca79aac71e.png)

**点击按钮后:**
![](img/7b253159704af03f7e6b2b65cce51b77.png)

**支持的浏览器:**T2 DOM 输入月份名称属性支持的浏览器如下:

*   谷歌 Chrome
*   Internet Explorer 10.0 +
*   火狐浏览器
*   歌剧
*   旅行队

**注意:**在 Firefox 中，输入 type="month "元素不显示任何日期字段或日历。