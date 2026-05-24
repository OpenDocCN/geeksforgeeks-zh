# 如何使用 HTML 和 CSS 在文本上创建流畅的归档效果？

> 原文:[https://www . geesforgeks . org/how-create-liquid-filing-effect-on-text-use-html-and-CSS/](https://www.geeksforgeeks.org/how-to-create-liquid-filing-effect-on-text-using-html-and-css/)

![](img/8fa3c9dde3139be08346c9df804be9d0.png)

液体填充文本动画可以使用**[CSS |:](https://www.geeksforgeeks.org/css-before-selector/)选择器**前完成。我们将使用关键帧来设置动画每一帧的高度。在尝试此代码之前，请确保您了解 **[CSS |:::在选择器](https://www.geeksforgeeks.org/css-before-selector/)** 和**[CSS | @关键帧规则](https://www.geeksforgeeks.org/css-keyframes-rule/)** 之前。

文本的基本样式可以有所不同，这完全取决于您希望文本的外观。主要是关键帧。对于前半部分的百分比，我们增加高度，对于后半部分，我们降低高度。我们使用了 25%作为高度的最小值。您可以使用百分比值来根据需要更改动画的最小和最大高度以及外观和感觉。

**创建结构:**在本节中，我们将创建文本，在其中我们将应用液体填充效果。要创建结构正常的 HTML 将是必需的。

*   **HTML 代码:**

    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8" />
        <meta name="viewport"
            content="width=device-width, initial-scale=1.0" />
        <title>Document</title>
    </head>
    <body>
        <center>
            <h1>GeeksforGeeks</h1>
        </center>
    </body>
    </html>                    
    ```

**设计结构:**在开始设计之前，你必须熟悉 CSS 中的几个概念，比如 **[CSS |:::在选择器](https://www.geeksforgeeks.org/css-before-selector/)** 和**[CSS | @关键帧规则](https://www.geeksforgeeks.org/css-keyframes-rule/)** 之前。其他效果完全取决于设计师。

*   **CSS 代码:**

    ```html
    <style>
        body {
            margin: 0;
            padding: 0;
        }

        h1 {
            margin: 200px 0;
            padding: 0;
            font-size: 80px;
            position: relative;
            color:green;
        }

        h1:before {
            content: "GeeksforGeeks";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            color:white;
            overflow: hidden;
            animation: animate 6s infinite;
        }

        @keyframes animate {
            0% {
            height: 25%;
            }
            25% {
            height: 50%;
            }
            50% {
            height: 65%;
            }
            75% {
            height: 40%;
            }
            100% {
            height: 25%;
            }
        }
    </style>
    ```

**最终解决方案:**在本节中，我们将以上两个部分合并为一个部分，实现对文本的液体填充效果。

*   **程序:**

    ```html
    <!DOCTYPE html>
    <html lang="en">

    <head>
        <meta charset="UTF-8" />
        <meta name="viewport" content=
            "width=device-width, initial-scale=1.0" />
        <title>
            How to Create Liquid Filing Effect
            on Text using HTML and CSS ?    
        </title>

        <style>
            body {
                margin: 0;
                padding: 0;
            }

            h1 {
                margin: 200px 0;
                padding: 0;
                font-size: 80px;
                position: relative;
                color:green;
            }

            h1:before {
                content: "GeeksforGeeks";
                position: absolute;
                top: 0;
                left: 0;
                width: 100%;
                height: 100%;
                color:white;
                overflow: hidden;
                animation: animate 6s infinite;
            }

            @keyframes animate {
                0% {
                height: 25%;
                }
                25% {
                height: 50%;
                }
                50% {
                height: 65%;
                }
                75% {
                height: 40%;
                }
                100% {
                height: 25%;
                }
            }
        </style>
    </head>

    <body>
        <center>
            <h1>GeeksforGeeks</h1>
        </center>
    </body>

    </html>
    ```

*   **输出:** ![](img/3f3848fd0180f89cb8be2327f9e5698a.png)