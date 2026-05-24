# CSS |边框-顶部样式属性

> 原文:[https://www . geesforgeks . org/CSS-border-top-style-property/](https://www.geeksforgeeks.org/css-border-top-style-property/)

**边框-顶部样式**属性用于指定顶部边框的样式。

**语法:**

```html
border-top-style: none | dotted | dashed | solid | groove | inset | 
outset | ridge | double | hidden | initial | inherit;
```

**默认值:**默认值为*无*。

**属性值**

1.  **无:**为默认值，使上边框宽度为零。因此，它是不可见的。
    **语法:**

```html
border-top-style:none;
```

**示例-1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        CSS | border-top-style Property
    </title>
    <style>
        h3.a {
            border-top-style: none;
        }
    </style>
</head>

<body>
    <h3 class="a">GeeksforGeeks </h3>
</body>

</html>
```

**输出:**
![](img/047278999b66d8175fc8daf522a05c24.png)

*   **Dotted:** It is used to make the top border with a series of dots.
    **Syntax:**

    ```html
    border-top-style:dotted;
    ```

    **示例-2:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            CSS | border-top-style Property
        </title>
        <style>
            h3.a {
                border-top-style: dotted;
            }
        </style>
    </head>

    <body>
        <h3 class="a">GeeksforGeeks </h3>
    </body>

    </html>
    ```

    **输出:**
    ![](img/01ae3a2c310f98547bc4bf7b8649a04b.png)

    *   **Dashed:** It makes the top border with a series of short line segments.
    **Syntax:**

    ```html
    border-top-style:dashed;
    ```

    **示例-3:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            CSS | border-top-style Property
        </title>
        <style>
            h3.a {
                border-top-style: dashed;
            }
        </style>
    </head>

    <body>
        <h3 class="a">GeeksforGeeks </h3>
    </body>

    </html>
    ```

    **输出:**

    ![](img/aa5a32d6cf0098b70872f6bad5bdcb42.png)

    *   **Solid:** It is used to make the top border with a single solid line segment.

    **语法:**

    ```html
    border-top-style:solid;
    ```

    **示例-4:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            CSS | border-top-style Property
        </title>
        <style>
            h3.a {
                border-top-style: solid;
            }
        </style>
    </head>

    <body>
        <h3 class="a">GeeksforGeeks </h3>
    </body>

    </html>
    ```

    **输出:**

    ![](img/a6b80ec59953e610ac9f9ee778d10549.png)

    *   **Groove:** It makes the top border with a grooved line segment, which makes us feel that it is going inside.

    **语法:**

    ```html
    border-top-style:groove;
    ```

    **示例-5:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            CSS | border-top-style Property
        </title>
        <style>
            h3.a {
                border-top-style: groove;
            }
        </style>
    </head>

    <body>
        <h3 class="a">GeeksforGeeks </h3>
    </body>

    </html>
    ```

    **输出:**
    ![](img/d172d3de65f41a3eab1d2c8f00e62e80.png)

    *   **Inset:** It makes the top border with an embedded line segment which makes us feel that it is fixed deeply on the screen.

    **语法:**

    ```html
    border-top-style:inset;
    ```

    **示例-6:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            CSS | border-top-style Property
        </title>
        <style>
            h3.a {
                border-top-style: inset;
            }
        </style>
    </head>

    <body>
        <h3 class="a">GeeksforGeeks </h3>
    </body>

    </html>
    ```

    **输出:**
    ![](img/815e838371bd39039bf0be8b0d26e8a0.png)

    *   **Outset:** It is the opposite of inset. It makes the top border with a line segment, which appears it to be coming out.

    **语法:**

    ```html
    border-top-style:outset;
    ```

    **示例-7:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            CSS | border-top-style Property
        </title>
        <style>
            h3.a {
                border-top-style: outset;
            }
        </style>
    </head>

    <body>
        <h3 class="a">GeeksforGeeks </h3>
    </body>

    </html>
    ```

    **输出:**
    ![](img/01574d6f80fa7d32e13130736912932f.png)

    *   **Ridge:** It is the opposite of groove. It makes the top border with a ridged line segment, which makes us feel that it is coming out.

    **语法:**

    ```html
    border-top-style:ridge;
    ```

    **示例-8:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            CSS | border-top-style Property
        </title>
        <style>
            h3.a {
                border-top-style: ridge;
            }
        </style>
    </head>

    <body>
        <h3 class="a">GeeksforGeeks </h3>
    </body>

    </html>
    ```

    **输出:**
    ![](img/4a8de8e8e5b92b5dc0cccfb93a68d461.png)

    *   **Double:** It makes the top border with a double solid line. The border width, in this case, is equal to the sum of widths of the two-line segments and the space between them.

    **语法:**

    ```html
    border-top-style:double;
    ```

    **示例-9:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            CSS | border-top-style Property
        </title>
        <style>
            h3.a {
                border-top-style: double;
            }
        </style>
    </head>

    <body>
        <h3 class="a">GeeksforGeeks </h3>
    </body>

    </html>
    ```

    **输出:**
    ![](img/c7ca60944e1479264ba993de13317b56.png)

    *   **Hidden:** It is used to make the top border invisible, like *none*, except in case of border conflict resolution of table elements.

    **语法:**

    ```html
    border-top-style:hidden;
    ```

    **示例-10**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            CSS | border-top-style Property
        </title>
        <style>
            h3.a {
                border-top-style: hidden;
            }
        </style>
    </head>

    <body>
        <h3 class="a">GeeksforGeeks </h3>
    </body>

    </html>
    ```

    **输出:**
    ![](img/b09e9bf455146f541a08b99b7b6ccaca.png)

    *   **Initial:** It is used to sets the default value of the element.

    **语法:**

    ```html
    border-top-style:initial;
    ```

    **例:11**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            CSS | border-top-style Property
        </title>
        <style>
            h3 {
                border-top-style: initial;
            }

        </style>
    </head>

    <body>
        <h3>GeeksforGeeks </h3>
    </body>

    </html>
    ```

    **输出:**
    ![](img/047278999b66d8175fc8daf522a05c24.png)

    *   **Inherit:** It makes the *top-border-style* property to be inherited from its parent element.

    **语法:**

    ```html
    border-top-style:inherit;
    ```

    **例:12**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            CSS | border-top-style Property
        </title>
        <style>
            h3 {
                border-top-style: inherit;
            }

            body {
                border-top-style: dotted;
            }
        </style>
    </head>

    <body>
        <h3>GeeksforGeeks </h3>
    </body>

    </html>
    ```

    **输出:**
    ![](img/9cdf502d53ee97040ae6e83b7b3f6b2c.png)

    **注意:**使用边框-顶部属性时，此属性是必需的。

    **支持的浏览器:***边框顶样式属性*支持的浏览器如下:

    *   谷歌 Chrome
    *   边缘
    *   Mozilla Firefox
    *   歌剧
    *   旅行队