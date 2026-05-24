# HTML5 MathML 罗琳属性

> 原文:[https://www . geesforgeks . org/html 5-mathml-rowlines-attribute/](https://www.geeksforgeeks.org/html5-mathml-rowlines-attribute/)

此属性保存行边框值，可以使用空格分隔多个值也可以考虑。可能的值是无、实线和虚线。该属性仅被 [<可移动>](https://www.geeksforgeeks.org/html5-mathml-mtable-tag/) 标签接受。

**语法:**

```html
<element rowlines="none|solid|dashed">
```

**属性值:**

*   **无:**该属性将表的行行设置为无。
*   **实体:**该属性设置表格实体的行线。
*   **虚线:**该属性设置表格虚线的行线。

以下示例说明了 HTML5 中的**罗琳**属性:

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title>HTML5 MathML rowlines Attribute</title> 
</head> 

<body> 
    <center> 
        <h1 style="color:green"> 
            GeeksforGeeks 
        </h1> 

        <h3>HTML5 MathML rowlines Attribute</h3> 

        <math> 
            <mi>GeeksforGeeks</mi> 
            <mo>=</mo> 
            <mtable frame="solid" rowlines="dashed"
                rowalign="bottom"> 

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

![](img/8a7206b955daa81d4a1bc4fff81d7701.png)

**支持的浏览器:**html 5 MathML 罗琳属性支持的浏览器如下:

*   火狐浏览器