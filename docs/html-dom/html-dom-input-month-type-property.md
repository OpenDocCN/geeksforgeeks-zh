# HTML | DOM 输入月份类型属性

> 原文:[https://www . geesforgeks . org/html-DOM-input-month-type-property/](https://www.geeksforgeeks.org/html-dom-input-month-type-property/)

**DOM 输入月份类型**属性用于返回月份字段是哪种类型的表单元素。

**语法:**

```html
monthObject.type
```

**返回值:**返回一个字符串值，代表月字段的形式元素类型。

**下面的程序说明了月份类型属性:**

**示例:**返回月字段的表单元素类型。

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        HTML DOM Input Month type Property
    </title> 
</head> 

<body style="text-align:center;"> 

    <h1>GeeksForGeeks</h1> 

    <h2>DOM Input Month type Property</h2> 
            <form id="myGeeks">
    <input type="month" id="month_id" name="geeks" > 
                 </form>
                 <br>
    <button onclick="myGeeks()">Click Here!</button> 

    <p id="GFG" style="font-size:20px;"></p> 

    <!-- Script to return the type Property-->
    <script> 
        function myGeeks() { 
            var gfg = document.getElementById("month_id").type;
            document.getElementById("GFG").innerHTML = gfg;
        } 
    </script> 
</body> 

</html>                     
```

**输出**
**点击按钮前:**
![](img/620026e0e6e1e1c94b67b4797fbc6052.png)

**点击按钮后:**
![](img/3f5e4721a7bc6629892970dd11e99aac.png)

**支持的浏览器:**T2 DOM 输入月份类型属性支持的浏览器如下:

*   谷歌 Chrome
*   Internet Explorer 10.0 +
*   火狐浏览器
*   歌剧
*   旅行队

**注意:**在 Firefox 中，输入 type="month "元素不显示任何日期字段或日历。