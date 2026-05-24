# HTML | DOM 输入周只读属性

> 原文:[https://www . geesforgeks . org/html-DOM-input-week-readonly-property/](https://www.geeksforgeeks.org/html-dom-input-week-readonly-property/)

HTML DOM 中的 **DOM 输入周只读**属性用于设置或返回输入周字段是否为只读。
可以复制，但不能修改。

**语法:**

*   它返回 readOnly 属性。

    ```html
    weekObject.readOnly
    ```

*   它用于设置 readOnly 属性。

    ```html
    weekObject.readOnly = "true|false"
    ```

**属性值:**

*   **true:** 设置周字段的 readOnly 属性。
*   **false:** 为默认值。它定义了周字段不是只读的。

**返回值:**返回一个布尔值，代表周字段是否为只读。

**示例-1:** 本示例返回输入周只读属性。

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        HTML DOM Input Week readOnly Property
    </title> 
</head> 

<body style="text-align:center;"> 

    <h1>GeeksForGeeks</h1> 

    <h2>DOM Input Week readOnly Property</h2> 
            <form id="myGeeks">
    <input type="week" id="week_id" name="geeks" readOnly> 
                 </form>
                 <br>
    <button onclick="myGeeks()">Click Here!</button> 

    <p id="GFG" style="font-size:20px;"></p> 

    <!-- Script to return the readOnly property-->
    <script> 
        function myGeeks() { 
            var gfg = document.getElementById("week_id").readOnly;
            document.getElementById("GFG").innerHTML = gfg;
        } 
    </script> 
</body> 

</html>                     
```

**输出**
**点击按钮前:**
![](img/9b7117f07616bade8803e24b9903e9f5.png)

**点击按钮后:**
![](img/c3d6691d99ead46fdac46459d071fb6f.png)

**示例-2:** 本示例说明如何**设置或更改**只读属性。

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        HTML DOM Input Week readOnly Property
    </title> 
</head> 

<body style="text-align:center;"> 

    <h1>GeeksForGeeks</h1> 

    <h2>DOM Input Week readOnly Property</h2> 
            <form id="myGeeks">
    <input type="week" id="week_id" name="geeks" readOnly> 
                </form>
                <br>
    <button onclick="myGeeks()">Click Here!</button> 

    <p id="GFG" style="font-size:20px;"></p> 

    <!-- Script to set the readOnly Property-->
    <script> 
        function myGeeks() { 
            var gfg = document.getElementById("week_id");
            gfg.readOnly = false;
            var g =    gfg.readOnly;        
            document.getElementById("GFG").innerHTML = g;
        } 
    </script> 
</body> 

</html>                    
```

**输出:**
**点击按钮前:**
![](img/9b7117f07616bade8803e24b9903e9f5.png)

**点击按钮后:**
![](img/ff70f30524187345102231caa6957ffb.png)

**支持的浏览器:**T2 DOM 输入周只读属性支持的浏览器如下:

*   谷歌 Chrome
*   Internet Explorer 10.0 +
*   火狐浏览器
*   歌剧
*   旅行队

**注意:**在 Firefox 中，输入 type="week "元素不显示任何日期字段或日历。