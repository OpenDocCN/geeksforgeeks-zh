# HTML | DOM 输入日期时间本地步进()方法

> 原文:[https://www . geesforgeks . org/html-DOM-input-datetime local-step-method/](https://www.geeksforgeeks.org/html-dom-input-datetimelocal-stepup-method/)

HTML DOM 中的 **Input DatetimeLocal stepUp()方法**用于将 Local datetime 字段的值增加一个指定的数字。输入日期时间本地递增()方法只能用于分钟值。年、月、日、小时、秒或毫秒不受 stepUp()方法的影响。

**语法:**

```html
datetimelocalObject.stepUp( number )
```

**参数:**该方法接受单参数**数**，用于指定本地日期时间字段应增加的分钟数。

下面的程序说明了 HTML DOM 中的 DatetimeLocal stepUp 属性:

**示例:**本示例使用 stepUp()方法将分钟值增加 2。

```html
<!DOCTYPE html>
<html>

<head> 
    <title>
        Input DatetimeLocal stepUp() Method
    </title> 
</head>

<body style="text-align:center;">

    <h1 style="color:green;">
        GeeksforGeeks
    </h1> 

    <h2 style="font-family: Impact;"> 
        Input DatetimeLocal stepUp() Method
    </h2>

    <input type="datetime-local" id="test_DatetimeLocal">

    <p>
        To increase the value of the datetimeLocal field
        by 2minutes, double click the "Update" button.
    </p>

    <button ondblclick="My_DatetimeLocal()">
        Update
    </button>

    <!-- Script to use stepUp() method -->
    <script>
        function My_DatetimeLocal() {
            document.getElementById("test_DatetimeLocal").stepUp(2);
        }
    </script>
</body>

</html>                    
```

**输出:**
**点击按钮前:**
![](img/21e879e72158baf51ac95cd38ccf68d7.png)
**点击按钮后:**
![](img/423d78385c29612ca80404001346ca59.png)

**支持的浏览器:**下面列出了*输入法*支持的浏览器:

*   苹果 Safari
*   Internet Explorer 12.0
*   谷歌 Chrome
*   歌剧