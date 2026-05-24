# 如何使用 jQuery 获取特定选项标签的文本？

> 原文:[https://www . geesforgeks . org/how-to-get-text-of-specific-option-tag-use-jquery/](https://www.geeksforgeeks.org/how-to-get-text-of-specific-option-tag-using-jquery/)

为了选择所选选项或任何特定选项的文本，jQuery 允许通过其特定的选择器轻松地进行选择。选择器用于选择特定元素。

**示例:**本示例选择特定选项(GFG_2)标签的文本。

```html
<!DOCTYPE html>  
<html>  

<head> 
    <title> 
        Get text of specific option tag
    </title>

    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/2.1.1/jquery.min.js">
    </script>
</head> 

<body style = "text-align:center;">  

    <h1 style = "color:green;" >  
        GeeksForGeeks  
    </h1>  

    <select id='GFG_list'>
        <option value='GFG_1'>GFG_A</option>
        <option value='GFG_2'>GFG_B</option>
        <option value='GFG_3'>GFG_C</option>
    </select>

    <br><br>

    <button id="GFG_Button" onclick = "getText()">
        getText
    </button> 

    <p id = "GFG_P" style="color:green;font-size:20px;"></p>

    <script>
        function getText(){
            var el = document.getElementById("GFG_P");
            el.innerHTML = $("#GFG_list option[value='GFG_2']").text();
        }
    </script> 
</body>  

</html>  
```

**输出:**

*   **点击按钮前:**
    ![](img/a4fe8f1205ba11f6597231230c30b3c7.png)
*   **点击按钮后:**
    ![](img/04b078c434bcd2ee0688a3e409d0389a.png)

**示例:**本示例选择当前所选选项标签的文本。

```html
<!DOCTYPE html>  
<html>  

<head> 
    <title> 
        Get text of specific option tag
    </title>

    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/2.1.1/jquery.min.js">
    </script>
</head> 

<body style = "text-align:center;">  

    <h1 style = "color:green;" >  
        GeeksForGeeks  
    </h1>  

    <select id='GFG_list'>
        <option value='GFG_1'>GFG_A</option>
        <option value='GFG_2'>GFG_B</option>
        <option value='GFG_3'>GFG_C</option>
    </select>

    <br><br>

    <button id="GFG_Button" onclick = "getText()">
        getText
    </button> 

    <p id = "GFG_P" style = "color:green; font-size: 20px;"></p>

    <script>
        function getText(){
            var el = document.getElementById("GFG_P");
            el.innerHTML = $("#GFG_list option:selected").text();
        }
    </script> 
</body>  

</html> 
```

**输出:**

*   **点击按钮前:**
    ![](img/5f0f20190273c86b94bdfa4b11892fff.png)
*   **点击按钮后:**
    ![](img/40ff8dc059eeea90997208cd9cc7cf6c.png)