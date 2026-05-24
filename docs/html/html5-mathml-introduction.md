# HTML5 | MathML 简介

> 原文:[https://www.geeksforgeeks.org/html5-mathml-introduction/](https://www.geeksforgeeks.org/html5-mathml-introduction/)

**MathML** 出现在 HTML5 中，目前的 MathML 版本是 3，它是在 2015 年推出的。MathML 代表数学标记语言。它像其他 HTML 元素一样，用于在网络浏览器中表示数学等式或表达式。MathML 的第一个版本于 1998 年发布，之后的第二个版本已经发布。基本上，MathML 是一个复杂的数学公式或方程可视化表示变得容易。HTML5 支持 MathML，所有的 MathML 标签必须在 **<【数学】>** 和**</数学>** 标签中使用。

MathML 用于描述数学，作为机器对机器通信的基础，它旨在由专门的创作工具处理，如方程编辑器，它对其他应用程序也有意义。

**MathML 不支持:**

*   MathML 不是计算或求解复杂方程的计算器，它只是显示方程的一种方式。
*   它不是一种编程语言，而是一种数学标记语言。

**MathML 有能力:**

*   MathML 可以用来表示矩阵形式。
*   MathML 可以用来表示偏微分方程。
*   MathML 可以用来表示化学反应方程式。

下面的例子给你一个关于 **MathML** :
**例子:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>HTML5 MathML</title>
</head>

<body style="text-align:center;">

    <h1 style="color:green"> 
        GeeksforGeeks 
    </h1>

    <h3>HTML5 MathML</h3>

    <!--start tag of the whole representation-->
    <math>

        <!-- Creating Matrix -->
        <mrow>
            <mi>A</mi>
            <mo>=</mo>

            <mfenced open="[" close="]">

                <mtable>
                    <mtr>
                        <mtd>
                            <mi>a</mi>
                        </mtd>
                        <mtd>
                            <mi>b</mi>
                        </mtd>
                    </mtr>

                    <mtr>
                        <mtd>
                            <mi>x</mi>
                        </mtd>
                        <mtd>
                            <mi>y</mi>
                        </mtd>
                    </mtr>

                </mtable>

            </mfenced>
        </mrow>

        <!-- Creating equation -->
        <br><br>
        <msub>
            <mi>Geeks</mi>
            <mn>4</mn>
        </msub>
        <mo>+</mo>
        <mn>Geeks</mn>
        <mo>=</mo>
        <msub>
            <mi>G</mi>
        </msub>
        <mo>→</mo>
        <msub>
            <mi>e</mi>
            <mn>2</mn>
        </msub>
        <mo>→</mo>
        <mi>k</mi>
        <mi>s</mi>
        <mn>4
        </mn>
        <msub>
            <mi>G</mi>
        </msub>
        <mo>→</mo>
        <msub>
            <mi>e</mi>
            <mn>2</mn>
        </msub>
        <mo>→</mo>
        <mi>k</mi>
        <mi>s</mi>
    </math>
</body>

</html>
```

**输出:**
![](img/2bd166c025f040b326550042991c9be2.png)
**注:**几乎有 30+ MathML 标签可用。下面以表格形式列出了所有标签:

| 标签 | 描述 |
| [MathML <数学>标签](https://www.geeksforgeeks.org/html5-mathml-math-tag/) | 你想使用的 MathML 元素应该被包装在<math>标签里面。</math> |
| math ml<maction>天 | 这个标记用于显示任何表达式的绑定动作。 |
| [MathML <菜单关闭>标签](https://www.geeksforgeeks.org/html5-mathml-menclose-tag/) | 此标记用于呈现符号属性指定的封闭符号内部的内容。 |
| [mathml<mererror>天](https://www.geeksforgeeks.org/html5-mathml-merror-tag/) | 这个标签用于将表达式包装在一个框中，使该表达式引人注目。 |
| [MathML <内嵌>标签](https://www.geeksforgeeks.org/html5-mathml-mfenched-tag/) | 该标记用于添加自定义的开括号和闭括号。 |
| [MathML < mfrac >日](https://www.geeksforgeeks.org/html5-mathml-mfrac-tag/) | 该标签用于在两位数或等式之间添加分数符号。 |
| [MathML < mglyph >日](https://www.geeksforgeeks.org/html5-mathml-mglyph-tag/) | 此标记仅用于 Unicode 字符上不可用的字符或符号。 |
| [MathML < mi >标签](https://www.geeksforgeeks.org/html5-mathml-mi-tag/) | 该标签用作标识符，例如任何种类的符号或功能。您可以在这个标签中放入任何语句。 |
| [mathml<mlbeledr>日](https://www.geeksforgeeks.org/html5-mathml-mlabeledtr-tag/) | 该标签用于表示一行中的标签，位于<mtable>元素的左侧或右侧。</mtable> |
| [MathML <免疫脚本>标签](https://www.geeksforgeeks.org/html5-mathml-mmultiscripts-tag/) | 该标签用于创建多维矩阵。程度取决于代表性阵列的条件。 |
| [MathML < mn >标签](https://www.geeksforgeeks.org/html5-mathml-mn-tag/) | 这个标签用来显示一个数字字符，它通常是一个带有可能的分隔符的数字序列。 |
| [MathML < mo >标签](https://www.geeksforgeeks.org/html5-mathml-mo-tag/) | 该标签用于元素之间的打印操作。这个标签可以使用任何类型的数学运算符。 |
| [MathML <推进器>标签](https://www.geeksforgeeks.org/html5-mathml-mover-tag/) | 此标记用于在表达式上附加重音符号或限制。 |
| [MathML <添加了>标签](https://www.geeksforgeeks.org/html5-mathml-mpadded-tag/) | 该标签用于添加额外的填充，并设置封装内容的位置和大小的一般调整。 |
| [MathML < mphantom >标签](https://www.geeksforgeeks.org/html5-mathml-mphantom-tag/) | 它被用来以不可见的方式渲染，但维度仍被保留。 |
| [mathml<mrboot>天](https://www.geeksforgeeks.org/html5-mathml-mroot-tag/) | 这个标记是用来显示像根乡绅一样的根的力量的。 |
| [MathML < mrow >天](https://www.geeksforgeeks.org/html5-mathml-mrow-tag/) | 这个标签用于创建一个包含一些数学表达式或任何随机文本的行。 |
| [MathML < ms >标签](https://www.geeksforgeeks.org/html5-mathml-ms-tag/) | 这个标签用于表示字符串，该字符串将通过编程语言和计算机代数系统来表示数学表达式。 |
| [MathML < mspace >标签](https://www.geeksforgeeks.org/html5-mathml-mspace-tag/) | 此标签用于打印空白。属性中必须提到空格的大小。 |
| [MathML < msqrt >天](https://www.geeksforgeeks.org/html5-mathml-msqrt-tag/) | 它用于显示元素内容的根占位符。 |
| [MathML <风格>标签](https://www.geeksforgeeks.org/html5-mathml-style-tag/) | 它是 HTML5 中的内置标签。此标签用于更改子元素的样式。 |
| math ml<msub>天 | 它用于打印任何表达式的基幂。 |
| [mathml<mssubup>天](https://www.geeksforgeeks.org/html5-mathml-msubsup-tag/) | 它用于打印基本功率和任何表达式的功率。 |
| math ml<msup>天 | 它用于在任何表达式上打印幂。 |
| [MathML < mtable >标签](https://www.geeksforgeeks.org/html5-mathml-mtable-tag/) | 这个标签类似于普通的 HTML 标签。

 |
| [MathML < mtd >天](https://www.geeksforgeeks.org/html5-mathml-mtd-tag/) | 该标签用于在 HTML5 中创建表格或矩阵的表格数据 |
| [MathML <多行文字>标记](https://www.geeksforgeeks.org/html5-mathml-mtext-tag/) | 此标签用于打印任何表达式前后的任何文本。 |
| [MathML <地铁>标签](https://www.geeksforgeeks.org/html5-mathml-mtr-tag/) | 该标签用于在 HTML5 中创建表格行或矩阵。 |
| [MathML < mth >天](https://www.geeksforgeeks.org/html5-mathml-mth-tag/) | 这个标签用于在 HTML5 中创建表格或矩阵的标题。 |
| [MathML <口>标签](https://www.geeksforgeeks.org/html5-mathml-munder-tag/) | 此标记用于在表达式下附加任何重音或限制。 |
| [mathml<munder>标签](https://www.geeksforgeeks.org/html5-mathml-munderover-tag/) | 该标记用于在表达式下面加上表达式上面附加任何重音或限制。 |
| [MathML <语义>标签](https://www.geeksforgeeks.org/html5-mathml-semantics-tag/) | 这个标签用于标记数学。标记数学有两种可能的方法 |

**支持的浏览器:****html 5 MathML 标签**支持的浏览器如下:

*   火狐浏览器