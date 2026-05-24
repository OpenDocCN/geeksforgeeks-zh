# CSS border-left-width 属性

> 原文：[https://www.geeksforgeeks.org/css-border-left-width-property/](https://www.geeksforgeeks.org/css-border-left-width-property/)

`border-left-width` 属性用于设置元素左边框的宽度。必须在 `border-left-color` 属性之前声明 `border-style` 或 `border-left-style` 属性。

**语法：**

```html
border-left-width: medium|thin|thick|length|initial|inherit;
```

## 属性值

### medium
有默认值。它用于指定中等大小的左边框。

*   **语法：**

    ```html
    border-left-width:medium;
    ```

*   **例：**

    ```html
    <!DOCTYPE html>
    <html>
    <head>
        <title>
            CSS | border-left-width Property
        </title>
        <style>
            h1 {
                color: green;
            }
            h3 {
                border: solid green;
                border-left-width: medium;
                width: 50%;
            }
        </style>
    </head>
    <body>
        <center>
            <h1>GeeksForGeeks</h1>
            <h2>border-left-width:medium;</h2>
            <h3>GeeksForGeeks</h3>
            <p style="border-style:dotted;
                      border-left-width:medium;
                      width:70%;">
                It is a computer science portal for geeks.
            </p>
        </center>
    </body>
    </html>
    ```

*   **输出：**
    ![](img/0ab8a6eefd739a239457d848231f80c3.png)

### thin
指定一条细的左边框。

*   **语法：**

    ```html
    border-left-width:thin;
    ```

*   **例：**

    ```html
    <!DOCTYPE html>
    <html>
    <head>
        <title>
            CSS | border-left-width Property
        </title>
        <style>
            h1 {
                color: green;
            }
            h3 {
                border: solid green;
                border-left-width: thin;
                width: 50%;
            }
        </style>
    </head>
    <body>
        <center>
            <h1>GeeksForGeeks</h1>
            <h2>border-left-width:thin;</h2>
            <h3>GeeksForGeeks</h3>
            <p style="border-style:dotted;
                      border-left-width:thin;
                      width:70%;">
                It is a computer science portal for geeks.
            </p>
        </center>
    </body>
    </html>
    ```

*   **输出：**
    ![](img/c37c4ace88605d62a91ba5c13f6bbb79.png)

### thick
指定元素的左边框粗。

*   **语法：**

    ```html
    border-left-width:thick;
    ```

*   **例：**

    ```html
    <!DOCTYPE html>
    <html>
    <head>
        <title>
            CSS | border-left-width Property
        </title>
        <style>
            h1 {
                color: green;
            }
            h3 {
                border: solid green;
                border-left-width: thick;
                width: 50%;
            }
        </style>
    </head>
    <body>
        <center>
            <h1>GeeksForGeeks</h1>
            <h2>border-left-width:thick;</h2>
            <h3>GeeksForGeeks</h3>
            <p style="border-style:dotted;
                      border-left-width:thick;
                      width:70%;">
                It is a computer science portal for geeks.
            </p>
        </center>
    </body>
    </html>
    ```

*   **输出：**
    ![](img/188c0c21216b6502c9ef1e5388564cba.png)

### length
以像素为单位指定左边框的厚度。

*   **语法：**

    ```html
    border-left-width: length;
    ```

*   **例：**

    ```html
    <!DOCTYPE html>
    <html>
    <head>
        <title>
            CSS | border-left-width Property
        </title>
        <style>
            h1 {
                color: green;
            }
            h3 {
                border: solid green;
                border-left-width: 10px;
                width: 50%;
            }
        </style>
    </head>
    <body>
        <center>
            <h1>GeeksForGeeks</h1>
            <h2>border-left-width:length;</h2>
            <h3>GeeksForGeeks</h3>
            <p style="border-style:dotted;
                      border-left-width:5px;
                      width:70%;">
                It is a computer science portal for geeks.
            </p>
        </center>
    </body>
    </html>
    ```

*   **输出：**
    ![](img/432ade5f49afece5ed0bfb12fbd948ad.png)

### initial
将属性设置为默认值。

*   **语法：**

    ```html
    border-left-width:initial;
    ```

*   **例：**

    ```html
    <!DOCTYPE html>
    <html>
    <head>
        <title>
            CSS | border-left-width Property
        </title>
        <style>
            h1 {
                color: green;
            }
            h3 {
                border: solid green;
                border-left-width: initial;
                width: 50%;
            }
        </style>
    </head>
    <body>
        <center>
            <h1>GeeksForGeeks</h1>
            <h2>border-left-width:initial;</h2>
            <h3>GeeksForGeeks</h3>
            <p style="border-style:dotted;
                      border-left-width:initial;
                      width:70%;">
                It is a computer science portal for geeks.
            </p>
        </center>
    </body>
    </html>
    ```

*   **输出：**
    ![](img/70ab20da4f0b096074cbcb0573648a43.png)

## 支持的浏览器
CSS `border-left-width` 属性支持的浏览器如下：

*   谷歌 Chrome 1.0
*   Internet Explorer 4.0
*   Firefox 1.0
*   歌剧 3.5
*   苹果 Safari 1.0