# HTML5 | MathML <msub>标签</msub>T3】

> 原文:[https://www.geeksforgeeks.org/html5-mathml-msub-tag/](https://www.geeksforgeeks.org/html5-mathml-msub-tag/)

HTML 中的 **MathML < msub >** 标签用于打印任意表达式的基幂。

**语法:**

```html
<msub> Contents </msub>
```

**属性:**该标签接受下面列出的一些属性:

*   **class|id|style:** 该属性保存内容的样式。
*   **数学背景:**该属性保存数学表达式背景颜色的值。
*   **href:** 该属性保存到指定网址的任何超链接。
*   **mathcolor:** 该属性保存数学表达式的颜色。
*   **下标移位:**该属性定义了将下标移位到表达式基线以下的最小空间。

以下示例说明了 HTML5 中的 MathML <msub>标记:
**示例:**</msub>

## 超文本标记语言

```html
!DOCTYPE html>
<html>

<head>
    <title>HTML5 MathML msub tag</title>
</head>

<body>
    <center>
        <h1 style="color:green">
            GeeksforGeeks
        </h1>

        <h3>HTML5 MathML <msub> tag</h3>

        <math>
            <mfenced open="(" close=")" separators="">
                <mrow>
                    <msub subscriptshift="5px">
                        <mi>x</mi>
                        <mn>2</mn>
                    </msub>
                    <mo>+</mo>
                    <msub>
                        <mi>y</mi>
                        <mn>2</mn>
                    </msub>
                    <mo>=</mo>
                    <msub subscriptshift="5px">
                        <mi>z</mi>
                        <mn>2</mn>
                    </msub>
                </mrow>
            </mfenched>
        </math>
    </center>
</body>

</html>                   
```

**输出:**

![](img/1c679f435e39e7db683ad53d16c8e85b.png)

**支持的浏览器:**以下列出了 **HTML5 MathML < msub >** 标签支持的浏览器:

*   火狐浏览器
*   旅行队