# HTML5 | MathML <mlabeledtr>标签</mlabeledtr>T3】

> 哎哎哎:# t0]https://www . geeksforgeeks . org/html 5-mathml-mlbeledr 标签/

HTML5 中的 **MathML < mlabeledtr >标签**用于表示一行中的标签，位于< mtable >元素的左侧或右侧。该元素的子元素类似于普通表，后面跟 m，像< td >变成< mtd >。
**语法:**

```html
<mlabeledtr> element </mlabeledtr>
```

**属性:**该标签接受以下列出的一些属性:

*   **class|id|style:** 该属性用于保存子元素的样式。
*   **href:** 此属性用于保存任何指向指定 URL 的超链接。
*   **数学背景:**该属性保存数学表达式背景颜色的值。
*   **mathcolor:** 该属性保存数学表达式的颜色。
*   **columnalign:** 该属性用于指定由< mtable >为该行指定的单元格的水平对齐。可能的值是**左**、**右**和**中**。
*   **rowalign:** 此属性用于指定由< mtable >为此行指定的单元格的垂直对齐方式。可能的值是**轴、基线、底部、中心**和**顶部**。

以下示例说明了 HTML5 中的 MathML <mlabeledtr>标记:
**示例:**</mlabeledtr> 

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>HTML5 MathML mlabeledtr tag</title>
</head>

<body>
    <center>
        <h1 style="color:green">
            GeeksforGeeks
        </h1>

        <h3>HTML5 MathML <mlabeledtr> tag</h3>

        <math>
            <mtable>
                <mlabeledtr>
                    <mtd>
                        <mn>X</mn>
                    </mtd>
                    <mtd>
                        <mi>Y</mi>
                    </mtd>
                    <mtd>
                        <mi>Z</mi>
                    </mtd>
                    <mtd>
                        <mn>W</mn>
                    </mtd>
                </mlabeledtr>

                <mtr>
                    <mtd>
                        <mi>P</mi>
                    </mtd>
                    <mtd>
                        <mi>Q</mi>
                    </mtd>
                    <mtd>
                        <mi>R</mi>
                    </mtd>
                    <mtd>
                        <mi>S</mi>
                    </mtd>
                    <mtd>
                        <mi>T</mi>
                    </mtd>
                </mtr>
            </mtable>
        </math>
    </center>
</body>

</html>
```