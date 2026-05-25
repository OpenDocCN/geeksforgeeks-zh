
# HTML5 MathML `rowalign` 属性

> 原文: [https://www.geeksforgeeks.org/html5-mathml-row-align-attribute/](https://www.geeksforgeeks.org/html5-mathml-row-align-attribute/)

此属性用于保持表格单元格的垂直对齐。可能的值包括顶部、底部和中心。该属性被 `<mtable>`、`<mtd>` 和 `<mtr>` 标签接受。

## 语法

```html
<element rowalign="top|bottom|center">
```

## 属性值

*   **顶部:** 设置行顶部的对齐方式。
*   **底部:** 设置行底部的对齐方式。
*   **中心:** 设置行中心的对齐方式。

## 示例

```html
<!DOCTYPE html> 
<html>

<head> 
    <title>HTML5 MathML rowalign Attribute</title> 
</head>

<body> 
    <center> 
        <h1 style="color:green"> 
            GeeksforGeeks 
        </h1>

<h3>HTML5 MathML rowalign Attribute</h3>

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

![Output](img/4859a7fe46710c879bdbc18dc2688b3c.png)

**支持的浏览器:** HTML5 MathML `rowalign` 属性支持的浏览器如下:

*   火狐浏览器
