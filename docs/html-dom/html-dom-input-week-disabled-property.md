# HTML | DOM 输入周禁用属性

> 原文:[https://www . geesforgeks . org/html-DOM-input-week-disabled-property/](https://www.geeksforgeeks.org/html-dom-input-week-disabled-property/)

HTML DOM 中的 **DOM 输入周禁用**属性用于返回一个布尔值，表示一个周字段是否应该禁用。
默认情况下，禁用的元素以灰色显示，不可用且不可点击。

**语法:**

*   它返回禁用的属性。

    ```html
    weekObject.disabled
    ```

*   它用于设置禁用属性。

    ```html
    weekObject.disabled = true
    ```

**属性值:**

*   **true:** 指定周字段被禁用。
*   **false:** 指定周字段未禁用。

**返回值:**返回布尔值，即如果周字段被禁用，则为真；如果周字段未被禁用，则为假。

**示例-1:** 本示例返回禁用属性的值。

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        HTML DOM Input Week disabled Property
    </title> 
</head> 

<body style="text-align:center;"> 

    <h1>GeeksForGeeks</h1> 

    <h2>DOM Input Week disabled Property</h2> 
            <form id="myGeeks">
    <input type="week" id="week_id" name="geeks" disabled> 
                 </form>
                 <br>
    <button onclick="myGeeks()">Click Here!</button> 

    <p id="GFG" style="font-size:20px;"></p> 

    <!-- Script to return the  value of disabled property-->
    <script> 
        function myGeeks() { 
            var gfg = document.getElementById("week_id").disabled;
            document.getElementById("GFG").innerHTML = gfg;
        } 
    </script> 
</body> 

</html>                     
```

**输出**
**点击按钮前:**
![](img/069b86414b3088c5c52d225d7b373303.png)

**点击按钮后:**
![](img/a09547d3fe0529387efe778b9d11f54f.png)

**示例-2:** 本示例说明如何**设置或更改**禁用属性。

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        HTML DOM Input Week disabled Property
    </title> 
</head> 

<body style="text-align:center;"> 

    <h1>GeeksForGeeks</h1> 

    <h2>DOM Input Week disabled Property</h2> 
            <form id="myGeeks">
    <input type="week" id="week_id" name="geeks" disabled> 
                </form>
                <br>
    <button onclick="myGeeks()">Click Here!</button> 

    <p id="GFG" style="font-size:20px;"></p> 

    <!-- Script to set the disabled attribute of week field-->
    <script> 
        function myGeeks() { 
            var gfg = document.getElementById("week_id");
            gfg.disabled = false;
            var g =    gfg.disabled;        
            document.getElementById("GFG").innerHTML = g;
        } 
    </script> 
</body> 

</html>                    
```

**输出:**
**点击按钮前:**
![](img/1b5486a30320c91566e3824d53bf669f.png)

**点击按钮后:**
![](img/3da21243b58973f291a22ab222db7591.png)

**支持的浏览器:**T2 DOM 输入周禁用属性支持的浏览器如下:

*   谷歌 Chrome
*   Internet Explorer 10.0 +
*   火狐浏览器
*   歌剧
*   旅行队

**注意:**在 Firefox 中，输入 type="week "元素不显示任何日期字段或日历。