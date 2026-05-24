# HTML | DOM 嵌入宽度属性

> 原文:[https://www . geesforgeks . org/html-DOM-embed-width-property/](https://www.geeksforgeeks.org/html-dom-embed-width-property/)

HTML 中的 **DOM 嵌入宽度属性**用于设置或返回宽度属性的值。宽度属性定义嵌入内容的宽度，以像素为单位。

**语法:**

*   **返回宽度属性:**

    ```html
    embedObj.width
    ```

*   **设置宽度属性:**

    ```html
    embedObj.width = pixels
    ```

**属性值:**

*   **px:** 以像素为单位指定嵌入内容的宽度。

**返回值:**返回一个数字，表示嵌入内容的宽度。

**示例:**

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title>HTML DOM Embed width Property</title> 
</head> 

<body> 
    <center> 
        <h1 style="color:green"> 
            GeeksforGeeks 
        </h1> 

        <embed id="embedID" width="400"
            src="https://ide.geeksforgeeks.org"> 
        <br> 
        <button onclick="GFGfun()"> 
            Try it 
        </button> 

        <p id="pid"></p> 

        <script> 
            function GFGfun() { 
                var idwidth = document.getElementById("embedID").width; 
                document.getElementById("pid").innerHTML = idwidth; 
            } 
        </script> 
    </center> 
</body> 

</html> 
```

**输出:**
**点击按钮前:**
![](img/f7b2e56de9b17a80fe95a23c3a3a2f43.png)
**点击按钮后:**
![](img/d03d9e09c6a50dd4d8cecd8bd58795a1.png)

**示例:**

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title>HTML DOM Embed width Property</title> 
</head> 

<body> 
    <center> 
        <h1 style="color:green"> 
            GeeksforGeeks 
        </h1> 

        <embed id="embedID"
            src="https://ide.geeksforgeeks.org"> 
        <br> 
        <button onclick="GFGfun()"> 
            Try it 
        </button> 

        <p id="pid"></p> 

        <script> 
            function GFGfun() { 
                var idwidth = 
                document.getElementById("embedID").width=400; 

                document.getElementById("pid").innerHTML
                     = idwidth; 
            } 
        </script> 
    </center> 
</body> 

</html> 
```

**输出:**
**点击按钮前:**
![](img/1354fe1f23a6a70fd37b957b7119c6fe.png)
**点击按钮后:**
![](img/90104a07a2dca27467049621fa618d50.png)

**支持的浏览器:****DOM 嵌入宽度属性**支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧