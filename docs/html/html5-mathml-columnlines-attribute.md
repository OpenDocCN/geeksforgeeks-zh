# HTML5 MathML 列线属性

> 原文:[https://www . geesforgeks . org/html 5-mathml-column lines-attribute/](https://www.geeksforgeeks.org/html5-mathml-columnlines-attribute/)

此属性保存列线的边框样式值。可能的值是*无*、*实心*和*虚线*。该属性仅被 [<可移动>](https://www.geeksforgeeks.org/html5-mathml-mtable-tag/) 标签接受。

**语法:**

```html
<element columnlines="none|solid|dashed">

```

**属性值:**

*   **无:**该属性将表的列线设置为“无”。
*   **实心:**该属性将表格的列线设置为“实心”。
*   **虚线:**该属性将表格的列线设置为“虚线”。

**示例:**下面的示例说明了 HTML5 中的*列线*属性。

## 超文本标记语言

```html
<!DOCTYPE html> 
<html> 

<body> 
    <center> 
        <h1 style="color:green"> 
            GeeksforGeeks 
        </h1> 

        <h3>HTML5 MathML columnlines Attribute</h3> 

        <math> 
            <mi>GeeksforGeeks</mi> 
            <mo>=</mo> 
            <mtable frame="solid" columnlines="dashed" 
                    columnaline="left" align="axis 1"> 
                <mtr mathbackground="green;"> 
                    <mtd>Course</mtd> 
                    <mtd>Fee</mtd> 
                </mtr> 
                <mtr> 
                    <mtd> 
                        <mi>C++ STL</mi> 
                    </mtd> 
                    <mtd> 
                        <mi> 1499</mi> 
                    </mtd> 
                </mtr> 
                <mtr> 
                    <mtd> 
                        <mi>Placement 100 </mi> 
                    </mtd> 
                    <mtd> 
                        <mi>9999 </mi> 
                    </mtd> 
                </mtr> 
                <mtr> 
                    <mtd> 
                        <mi>DSA Foundation </mi> 
                    </mtd> 
                    <mtd> 
                        <mi>7999</mi> 
                    </mtd> 
                </mtr> 
            </mtable> 
        </math> 
    </center> 
</body>
</html>
```

**输出:**

![](img/0d57bc618c17e8c32b7a3d581b55e9ab.png)

**支持的浏览器:**html 5 MathML*column line*属性支持的浏览器如下。

*   火狐浏览器