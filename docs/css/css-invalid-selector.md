# CSS |:无效选择器

> 原文:[https://www.geeksforgeeks.org/css-invalid-selector/](https://www.geeksforgeeks.org/css-invalid-selector/)

这:无效选择器用于选择每个不根据元素验证的表单元素**。
此选择器仅适用于某些有限制的表单元素，如具有最小和最大属性的输入元素、具有合法电子邮件的电子邮件字段或具有数值的数字字段等。不是使用:invalid 选择器，而是使用:valid 选择器来选择根据元素进行验证的表单元素。**

**语法:**

```html
:invalid {
    // CSS property
} 

```

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>invalid selector</title>
        <style>
            h1 {
                color:green;
            }
            input:invalid {
                border: 1px solid black;
                border-radius:4px;
                color:white;
                background-color:green;
                padding:5px;
            }
            body {
                text-align:center;
            }
        </style>
    </head>
    <body>
        <h1>GeeksforGeeks</h1>
        <h2>:invalid Selector</h2>
        Email Address: <input type="email" placeholder="abc@gfg.com">
    </body>
</html>                    
```

**输出:**
![](img/32c089f55c313a210004a82ccbd7784e.png)

**支持的浏览器:***支持的浏览器:无效的*选择器如下:

*   苹果 Safari 5.0
*   谷歌 Chrome 10.0
*   Firefox 4.0
*   opera10.0
*   Internet Explorer 10.0