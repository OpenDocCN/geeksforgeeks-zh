
# HTML 5 MathML Numerical Attribute

> 原文: [https://www.geeksforgeeks.org/html5-mathml-numerical-attribute/](https://www.geeksforgeeks.org/html5-mathml-numerical-attribute/)

The `numalign` attribute saves the alignment value of the numerator, with possible values being *left*, *right*, and *center*. This attribute is only accepted by the `<mfrac>` tag.

## Syntax:

```html
<element numalign="left|right|center">
```

## Attribute Values:

*   **Left:** This attribute sets the numerator to the left.
*   **Right:** This attribute sets the numerator to the right.
*   **Center:** This attribute sets the numerator to the center.

## Example:

The following example demonstrates the *numerical* attribute in HTML5 MathML.

## HyperText Markup Language

```html
<!DOCTYPE html> 
<html>

<body> 
    <center> 
        <h1 style="color:green"> 
            GeeksforGeeks 
        </h1>

<h3>HTML5 MathML numalign Attribute</h3>

<math> 
            <mfrac bevelled="true"> 
                <mfrac numalign="center"> 
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

**Output:**

![Output Image](img/26d77eeb8ab8cac4266af9343269107b.png)

**Supported Browsers:** The HTML 5 MathML *numerical* attribute is supported by the following browsers:

*   Firefox Browser
