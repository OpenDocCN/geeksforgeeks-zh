
# HTML5 MathML columnalign 属性

> 原文: [https://www.geeksforgeeks.org/html5-mathml-columnalign-attribute/](https://www.geeksforgeeks.org/html5-mathml-columnalign-attribute/)

该属性保持表格单元格的水平对齐。可能的值是左、右和中间。该属性被 `<mtable>` 、 `<mtd>` 、 `<mtr>` 和 `<mlabeledtr>` 标签接受。

## 语法:

```html
<element columnalign="left|right|center">
```

## 属性值:

*   **左侧:** 该属性设置每行上下文向左对齐。
*   **右侧:** 该属性将每行的上下文对齐设置为右侧。
*   **中心:** 该属性设置每行上下文到中心的对齐方式。

## 示例:

```html
<!DOCTYPE html> 
<html>

<head> 
    <title>HTML5 MathML columnalign Attribute</title> 
</head>

<body> 
    <center> 
        <h1 style="color:green"> 
            GeeksforGeeks 
        </h1>

<h3>HTML5 MathML columnalign Attribute</h3>

<math> 
            <mi>GeeksforGeeks</mi> 
            <mo>=</mo> 
            <mtable frame="solid" rowlines="dashed" 
                    columnalign="left" align="axis 1"> 
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

![Output](img/5588746c9eb06bbbb0b6f79a763a45f4.png)

**支持的浏览器:** HTML 5 MathML column align 属性支持的浏览器如下:

*   火狐浏览器
