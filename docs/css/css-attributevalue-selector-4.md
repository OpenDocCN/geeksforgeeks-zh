# CSS |[属性| =值]选择器

> 原文:[https://www . geesforgeks . org/CSS-attribute value-selector-4/](https://www.geeksforgeeks.org/css-attributevalue-selector-4/)

[attribute|=value]选择器用于选择属性值等于“value”的元素，或者属性值以“value”开头，后面紧跟连字符(-)。
**注:**使用<！在 IE8 或更早版本中运行[属性| =值]选择器。

**语法:**

```html
[attributeType|=value] {
    // CSS Property
}

```

**例 1:**

```html
<!DOCTYPE html> 
<html> 
    <head> 
        <title>
            CSS|[attribute|=value] Selector
        </title>

        <!-- CSS property -->
        <style>
            [class|=Geeks] {
                background-color:green;
                border: 5px solid green;
            }
        </style>
    </head> 

    <body style = "text-align: center;">

        <!-- CSS property apply here -->
        <h1 class = "Geeks">
            GeeksforGeeks
        </h1>

        <h3 class = "GeeksforGeeks">
            A computer science portal
        </h3>

        <!-- CSS property apply here -->
        <h2 class = "Geeks-portal">
            CSS [attribute|=value] Selector
        </h2>

    </body>
</html>                    
```

**输出:**
![](img/df9c33a14f60c4f4dc838204a63c2b2c.png)

**例 2:**

```html
<!DOCTYPE html> 
<html> 
    <head> 
        <title>
            CSS|[attribute|=value] Selector
        </title>

        <!-- CSS property -->
        <style>
            [id|=Geeks] {
                background-color:green;
                border: 5px solid green;
            }
        </style>
    </head> 

    <body style = "text-align: center;">

        <!-- CSS property apply here -->
        <h1 id = "Geeks">
            GeeksforGeeks
        </h1>

        <h3 id = "GeeksClasses">
            A computer science portal
        </h3>

        <!-- CSS property apply here -->
        <h2 id = "Geeks-portal">
            CSS [attribute|=value] Selector
        </h2>

    </body>
</html>                    
```

**输出:**
![](img/df9c33a14f60c4f4dc838204a63c2b2c.png)

**支持的浏览器:**T2【属性| =值】选择器支持的浏览器如下:

*   谷歌 Chrome 4.0
*   internet explorer 7.0
*   Firefox 2.0
*   苹果 Safari 3.1
*   歌剧 9.6