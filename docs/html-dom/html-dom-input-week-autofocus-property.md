# HTML | DOM 输入周自动对焦属性

> 原文:[https://www . geesforgeks . org/html-DOM-input-week-autofocus-property/](https://www.geeksforgeeks.org/html-dom-input-week-autofocus-property/)

HTML DOM 中的 **DOM 输入周自动对焦**属性用于设置或返回页面加载时输入周字段是否应该对焦。它反映了 HTML 自动对焦属性。

**语法:**

*   它返回自动对焦属性。

    ```html
    weekObject.autofocus
    ```

*   它用于设置自动对焦属性。

    ```html
    weekObject.autofocus = "true|false"
    ```

**属性值:**

*   **true:** 设置周场焦点。
*   **假:**有默认值。它定义了周字段没有得到关注。

**返回值:**返回一个布尔值，代表星期字段是否自动对焦。

**示例-1:** 本示例返回输入周自动对焦属性。

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        HTML DOM Input Week autofocus Property
    </title> 
</head> 

<body style="text-align:center;"> 

    <h1>GeeksForGeeks</h1> 

    <h2>DOM Input Week autofocus Property</h2> 
            <form id="myGeeks">
    <input type="week" id="week_id" name="geeks" autofocus> 
                 </form>
                 <br>
    <button onclick="myGeeks()">Click Here!</button> 

    <p id="GFG" style="font-size:20px;"></p> 

    <!-- Script to return the autofocus  Property-->
    <script> 
        function myGeeks() { 
            var gfg = document.getElementById("week_id").autofocus;
            document.getElementById("GFG").innerHTML = gfg;
        } 
    </script> 
</body> 

</html>                     
```

**输出**
**点击按钮前:**
![](img/5066bbcd664cd04ad103be8f6e4c4800.png)

**点击按钮后:**
![](img/e1c1a8edd94e69e892ca7232a6b87a41.png)

**示例-2:** 本示例说明如何**设置**属性。

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        HTML DOM Input Week autofocus Property
    </title> 
</head> 

<body style="text-align:center;"> 

    <h1>GeeksForGeeks</h1> 

    <h2>DOM Input Week autofocus Property</h2> 
            <form id="myGeeks">
    <input type="week" id="week_id" name="geeks" > 
                </form>
                <br>
    <button onclick="myGeeks()">Click Here!</button> 

    <p id="GFG" style="font-size:20px;"></p> 

    <!-- Script to set the autofocus Property-->
    <script> 
        function myGeeks() { 
            var gfg = document.getElementById("week_id");
            gfg.autofocus = true;
            var g =    gfg.autofocus;        
            document.getElementById("GFG").innerHTML = g;
        } 
    </script> 
</body> 

</html>                    
```

**输出:**
**点击按钮前:**
![](img/c73ff47c1a20702994f7796e52a9f15f.png)

**点击按钮后:**
![](img/18b94d8104c65f836aabbff686aadde6.png)

**支持的浏览器:**T2 DOM 输入周自动对焦属性支持的浏览器如下:

*   谷歌 Chrome
*   Internet Explorer 10.0 +
*   火狐浏览器
*   歌剧
*   旅行队

**注意:**在 Firefox 中，输入 type="week "元素不显示任何日期字段或日历。