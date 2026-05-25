
# HTML5 MathML 列间距属性

> 原文: [https://www.geeksforgeeks.org/html5-mathml-columnspacing-attribute/](https://www.geeksforgeeks.org/html5-mathml-columnspacing-attribute/)

该属性定义了表的列之间的空间。该属性仅被 `<mtable>` 标签接受。

## 语法:

```html
<element columnspacing="number">
```

## 属性值:

*   **编号:** 该属性定义列间的间距。

## 示例

```html
<!DOCTYPE html> 
<html>

<head> 
    <title>HTML5 MathML columnspacing Attribute</title> 
</head>

<body> 
    <center> 
        <h1 style="color:green"> 
            GeeksforGeeks 
        </h1>

<h3>HTML5 MathML columnspacing Attribute</h3>

<math> 
            <mi>GeeksforGeeks</mi> 
            <mo>=</mo> 
            <mtable frame="solid" columnlines="dashed" 
                    columnspacing="2" align="axis 1"> 
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

![输出示例](img/153bd03602e61649955285fe2c7417b4.png)

**支持的浏览器:** HTML5 MathML **栏间距**属性支持的浏览器如下:

*   火狐浏览器
