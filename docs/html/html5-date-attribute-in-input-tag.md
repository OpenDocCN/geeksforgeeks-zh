# HTML5 |日期属性在<input>标签

> 原文:[https://www . geesforgeks . org/html 5-输入标签中的日期属性/](https://www.geeksforgeeks.org/html5-date-attribute-in-input-tag/)

输入标签中的日期属性创建一个日历来选择日期，包括日、月和年。

**语法:**

```html
<input type = "date">
```

**示例 1:** 在输入标签中使用日期属性

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Date Attribute</title>
    </head>
    <body>
        <form action="/">
            Date of Birth: <input type = "date">
        </form>
    </body>
</html>                    
```

**输出:**
![Output1](img/19f444afebe452191b95c1c8d32cc10c.png)

**示例 2:** 初始化输入标签中的默认日期值。输入标签中的日期格式为 value =“yyyy-mm-DD”

```html
<html>
    <head>
        <title>Date Attribute</title>
    </head>
    <body>
        <form action="/">
            Date of Birth: <input type="date" value="2018-10-19">
        </form>
    </body>
</html>
```

**输出:**
![Output2](img/1703e93017ebf8a4c57eda3e22551472.png)

**示例 3:** 日期属性的 DOM

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Date Attribute</title>
    </head>
    <body>
        Date of Birth:
        <input type="date" id="dob">
        <button onclick="dateDisplay()">Submit</button>
        <p id="demo"></p>
        <script>
            function dateDisplay() {
                var x = document.getElementById("dob").value;
                document.getElementById("demo").innerHTML = x;
            }
        </script>
    </body>
</html>
```

**输出:**
![Output3](img/8f83ba909cc80a6d8135a62013fb71d5.png)

**手机中的输出:**
![Output4](img/1dcd173e0333ac1c380edbe6912e07f5.png)