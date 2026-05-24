# HTML | output 表单属性

> 原文:[https://www.geeksforgeeks.org/html-output-form-attribute/](https://www.geeksforgeeks.org/html-output-form-attribute/)

**HTML <输出>表单属性**用于指定<输出>元素可以包含一个或多个表单。

**语法:**

```html
<output form="form_id">
```

**属性值:**它包含单个值 **form_id** ，该值包含指定输出元素所属的一个或多个的值，即 form_id。该属性的值应该是<表单>元素的 id。

**示例:**

```html
<!DOCTYPE html> 
<html> 
    <head> 
        <title>
            HTML output Form Attribute
        </title> 

        <style> 
            body { 
                text-align:center; 
            } 
            h1 { 
                color:green; 
            } 
        </style> 
    </head> 

    <body> 
        <h1>GeeksforGeeks</h1> 

        <h2><output>Form Attribute</h2> 

        <form oninput = "sumresult.value = parseInt(A.value) 
                    + parseInt(B.value) + parseInt(C.value)"> 
            <input type = "number" name = "A" value = "50" /> + 
            <input type = "range" name = "B" value = "0" /> + 
            <input type = "number" name = "C" value = "30" /><br> 

            Result: <output form ="myGeeks" name = "sumresult">
            </output>
        </form> 
    </body> 
</html>                    
```

**输出:**
![](img/a8b19ec21e2796a09cf5d70f58bb3fe5.png)

**支持的浏览器:****HTML 输出表单属性**支持的浏览器如下:

*   谷歌 Chrome
*   火狐浏览器
*   歌剧
*   旅行队