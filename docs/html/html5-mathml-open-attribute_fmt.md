
# HTML5 MathML Open Attribute

> 原文: [https://www.geeksforgeeks.org/html5-mathml-open-attribute/](https://www.geeksforgeeks.org/html5-mathml-open-attribute/)

This attribute saves any equation's left parenthesis, similar to the close attribute. The attribute is accepted by the [<mfenced>](https://www.geeksforgeeks.org/html5-mathml-mfenched-tag/) tag.

**Syntax:**

```html
<element open="parentheses">
```

**Attribute Values:**

*   **Parentheses:** Saves the parentheses used to open any equation.

The following example demonstrates the open attribute in HTML5 MathML:

**Example**:

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>HTML5 MathML open attribute</title>
</head>

<body>
    <center>
        <h1 style="color:green">
            GeeksforGeeks
        </h1>

<h3>HTML5 MathML open attribute</h3>
        <math>
            <mfenced open="{" close="}" separators="">
                <mrow>
                    <msup>
                        <mi>x</mi>
                        <mn>2</mn>
                    </msup>
                    <mo>+</mo>
                    <msup>
                        <mi>y</mi>
                        <mn>2</mn>
                    </msup>
                    <mo>=</mo>
                    <msup>
                        <mi>z</mi>
                        <mn>2</mn>
                    </msup>
                </mrow>
                </mfenced>
        </math>
    </center>
</body>

</html>
```

**Output:**

![Output Image](https://www.geeksforgeeks.org/wp-content/uploads/2020/07/6527512eb04cfd29be3f8a5bfe9858d4.png)

**Supported Browsers:** The HTML5 MathML open attribute is supported by the following browsers:

*   Firefox browser
