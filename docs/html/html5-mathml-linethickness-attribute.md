# HTML5 MathML 线宽属性

> 原文:[https://www . geesforgeks . org/html 5-mathml-line thickness-attribute/](https://www.geeksforgeeks.org/html5-mathml-linethickness-attribute/)

该属性保存分数的厚度值。可能的值有**粗**、**中**和**细**。该属性仅被 [< mfrac >](https://www.geeksforgeeks.org/html5-mathml-mfrac-tag/) 标签接受。

**语法:**

```html
<element linethickness=="thin | medium | thick">
```

**属性值:**

*   **变细:**该属性设置线条粗细变细。
*   **中等:**该属性设置线宽中等。
*   **粗细:**该属性设置线条粗细粗细。

以下示例说明了 HRML5 MathML 中的线宽属性:

**示例:**

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title>HTML5 MathML linethickness Attribute</title> 
</head> 

<body> 
    <center> 
        <h1 style="color:green"> 
            GeeksforGeeks 
        </h1> 

        <h3>HTML5 MathML linethickness Attribute</h3> 

        <math> 
            <mfrac bevelled="true"
                   linethickness="thick"> 
                <mfrac> 
                    <msup> 
                        <mi>x</mi> 
                        <mn>2</mn> 
                    </msup> 
                    <msup> 
                        <mi>y</mi> 
                        <mn>2</mn> 
                    </msup> 
                </mfrac> 
                <mfrac> 
                    <msup> 
                        <mi>a</mi> 
                        <mn>2</mn> 
                    </msup> 
                    <msup> 
                        <mi>b</mi> 
                        <mn>2</mn> 
                    </msup> 
                </mfrac> 
            </mfrac> 
        </math> 
    </center> 
</body> 

</html> 
```

**输出:**

![](img/20a04e531293f6353ebfb99c38c4614d.png)

**支持的浏览器:**html 5 MathML 线宽属性支持的浏览器如下:

*   火狐浏览器