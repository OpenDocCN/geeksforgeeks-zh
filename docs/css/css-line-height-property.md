# CSS |行高属性

> 原文:[https://www.geeksforgeeks.org/css-line-height-property/](https://www.geeksforgeeks.org/css-line-height-property/)

CSS 中的**行高**属性用于设置用于行的空间量，例如在文本中。不允许负值。

**语法:**

```html
line-height: normal|number|length|percentage|initial|inherit;

```

**属性值**:

*   **normal:** This mode represents the normal line height. This is the default value.

    ```html
    line-height: normal;

    ```

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>CSS line-height Property</title>
            <style>
                .geek {
                  line-height: normal;
                  background: green;
                  color: white;
                }
            </style>
        </head>
        <body style = "text-align:center;">
            <h1 style = "color:green;">
                GeeksforGeeks
            </h1>

            <h2>
                CSS line-height Property
            </h2>

            <div class="geek">
                A computer science portal for geeks.<br>
                This div has line-height: normal;
            </div>
        </body>
    </html>
    ```

    **输出:**
    ![lineheight](img/c4a15273870318fd2aa29459b828a438.png)

*   **number:** This value is a unitless number multiplied with the current font-size to set the line height. In most cases, this is the preferred way to set line-height and avoid unexpected results due to inheritance.

    ```html
    line-height: number;

    ```

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>CSS line-height Property</title>
            <style>
                .geek {
                  line-height: 2.5;
                  background: green;
                  color: white;
                }
            </style>
        </head>
        <body style = "text-align:center;">
            <h1 style = "color:green;">
                GeeksforGeeks
            </h1>

            <h2>
                CSS line-height Property
            </h2>

            <div class="geek">
                A computer science portal for geeks.<br>
                This div has line-height: 2.5;
            </div>
        </body>
    </html>
    ```

    **输出:**
    ![lineheight](img/564c10cc326060e445caf92fa7cdce35.png)

*   **length:** In this mode a fixed line height is specified.

    ```html
    line-height: length;

    ```

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>CSS line-height Property</title>
            <style>
                .geek {
                  line-height: 2em;
                  background: green;
                  color: white;
                }
            </style>
        </head>
        <body style = "text-align:center;">
            <h1 style = "color:green;">
                GeeksforGeeks
            </h1>

            <h2>
                CSS line-height Property
            </h2>

            <div class="geek">
                A computer science portal for geeks.<br>
                This div has line-height: 2em;
            </div>
        </body>
    </html>
    ```

    **输出:**
    ![lineheight](img/82cbf6df1c68b420e214e367cfbcd12a.png)

*   **percentage:** This mode is used to set line height in percent of the current font size.

    ```html
    line-height: percentage;

    ```

    **例:**

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>CSS line-height Property</title>
            <style>
                .geek {
                  line-height: 150%;
                  background: green;
                  color: white;
                }
            </style>
        </head>
        <body style = "text-align:center;">
            <h1 style = "color:green;">
                GeeksforGeeks
            </h1>

            <h2>
                CSS line-height Property
            </h2>

            <div class="geek">
                A computer science portal for geeks.<br>
                This div has line-height: 150%;
            </div>
        </body>
    </html>
    ```

    **输出:**
    ![lineheight](img/0dc295dcf88694a2cae5de1a527495cc.png)

*   **初始:**该模式用于将该属性设置为默认值。
    **语法:**

    ```html
    line-height: initial;

    ```

**支持的浏览器:***行高属性*支持的浏览器如下:

*   谷歌 Chrome 1.0
*   Internet Explorer 4.0
*   Firefox 1.0
*   Opera 7.0
*   苹果 Safari 1.0