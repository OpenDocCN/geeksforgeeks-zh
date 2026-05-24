# jQuery |禁用/启用输入元素

> 原文:[https://www . geesforgeks . org/jquery-disable-enable-an-input-element/](https://www.geeksforgeeks.org/jquery-disable-enable-an-input-element/)

在 jQuery 中禁用/启用输入元素可以通过使用 prop()方法来完成。prop()方法用于设置或返回选定元素的属性和值。

**示例 1:** 本示例使用 **prop()方法**禁用输入文本字段。

```html
<!DOCTYPE html>  
<html>  

<head> 
    <title> 
        JavaScript enable/disable
        an input element
    </title>

    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
</head> 

<body style = "text-align:center;">  

    <h1 style = "color:green;" >  
        GeeksForGeeks  
    </h1>  

    <input id = "input" type="text" name="input"/> 

    <button onclick="enable_disable()"> 
        Enable/Disable
    </button> 

    <!-- Script to disable input text area -->
    <script> 
        function enable_disable() {
            $("input").prop('disabled', true);
        }
    </script> 
</body>  

</html>
```

**输出:**

*   **点击按钮前:**
    ![](img/bdfa7d6249a28e3b262516f80285e2e2.png)
*   **点击按钮后:**
    ![](img/e70c2a3e1c6bae1326fef38606c81f28.png)

**示例 2:** 本示例使用 **prop()方法**启用输入文本字段。

```html
<!DOCTYPE html>  
<html>  

<head> 
    <title> 
        JavaScript enable/disable
        an input element
    </title>

    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
</head> 

<body style = "text-align:center;">  

    <h1 style = "color:green;" >  
        GeeksForGeeks  
    </h1> 

    <input id = "input" type="text" name="input" disabled/> 

    <button onclick="enable_disable()"> 
        Enable/Disable
    </button> 

    <!-- Script to enable input text fields -->       
    <script> 
        function enable_disable() {
            $("input").prop('disabled', false);
        }
    </script> 
</body>  

</html>
```

**输出:**

*   **点击按钮前:**
    ![](img/e70c2a3e1c6bae1326fef38606c81f28.png)
*   **点击按钮后:**
    ![](img/bdfa7d6249a28e3b262516f80285e2e2.png)