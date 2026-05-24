# HTML | DOM 输入密码禁用属性

> 原文:[https://www . geesforgeks . org/html-DOM-输入-密码-禁用-属性/](https://www.geeksforgeeks.org/html-dom-input-password-disabled-property/)

**DOM 输入密码禁用属性**用于设置或返回输入密码字段是否必须**禁用**。禁用的密码字段不可点击且不可用。它是一个布尔属性，用于反映 HTML 禁用属性。在所有浏览器中，默认情况下，它通常呈现为灰色。

**语法:**

*   它用于返回禁用的属性。

    ```html
    passwordObject.disabled
    ```

*   它用于设置禁用属性。

    ```html
    passwordObject.disabled = true|false
    ```

**属性值:**

*   **真:**定义**输入密码字段**被禁用。
*   **False:** 有默认值。定义**输入密码字段**未禁用。

**返回值:**返回一个布尔值，表示**输入密码字段**是否被禁用。

**示例-1:** 这个示例说明了如何返回属性。

```html
<!DOCTYPE html> 
<html> 

<body style="text-align:center;"> 

    <h1 style="color:green;"> 
            GeeksForGeeks 
        </h1> 

    <h2>DOM Input Password disabled Property</h2> Password: 
    <input type="password"
        id="myPsw"
         disabled> 
    <br><br>
    <button onclick="myFunction()"> 
    Click Here! 
</button> 

    <p id="demo" style="color:green;font-size:25px;"></p> 

    <script> 
        function myFunction() { 
            var x = 
            document.getElementById( 
            "myPsw").disabled;

            document.getElementById( 
            "demo").innerHTML = x; 
        } 
    </script> 

</body> 

</html>                    
```

**输出:**
**点击按钮前:**
![](img/f3b9ffff7bd2bc244226d37bd5bbef88.png)
**点击按钮后:**
![](img/0505fabbe2677ff92b84c6523e71fee4.png)

**示例-2 :** 本示例说明如何**设置**属性。

```html
<!DOCTYPE html> 
<html> 

<body style="text-align:center;"> 

    <h1 style="color:green;"> 
            GeeksForGeeks 
        </h1> 

    <h2>DOM Input Password disabled Property</h2> Password: 
    <input type="password"
        id="myPsw"
         disabled> 
    <br><br>
    <button onclick="myFunction()"> 
    Click Here! 
</button> 

    <p id="demo" style="color:green;font-size:25px;"></p> 

    <script> 
        function myFunction() { 
            var x = 
            document.getElementById( 
            "myPsw").disabled =false;

            document.getElementById( 
            "demo").innerHTML = x; 
        } 
    </script> 

</body> 

</html>                    
```

**输出:**

**点击按钮前:**
![](img/f3b9ffff7bd2bc244226d37bd5bbef88.png)
**点击按钮后:**
![](img/4ec8bc6e6f16a8edda97545f89389943.png)

**支持的浏览器:**T2 DOM 输入密码禁用属性支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队