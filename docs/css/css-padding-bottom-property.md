# CSS 填充-底部属性

> 原文:[https://www.geeksforgeeks.org/css-padding-bottom-property/](https://www.geeksforgeeks.org/css-padding-bottom-property/)

元素的填充是其内容和边框之间的空间。底部填充 CSS 属性用于设置元素底部填充区域的高度。

**语法:**

```html
padding-bottom: length|percentage;
```

**属性值**:

*   **length:** This value is used to specify the size of padding as a fixed value. The default value is 0\. It must be non-negative.

    **语法:**

    ```html
    padding-bottom: length;
    ```

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>CSS padding-bottom Property</title>
            <style>
                p.geek {
                padding-bottom: 35px;
                color: white;
                background: green;
                }
            </style>
        </head>

        <body style = "text-align: center;">

            <h1 style = "color: green;">GeeksforGeeks</h1>

            <h2>padding-bottom Property</h2>

            <!-- Below paragraph element has a 
                padding-bottom of 35px -->
            <p class="geek">
                This paragraph has a padding-bottom: 35px;
            </p>

        </body>
    </html>                    
    ```

    **输出:**
    ![paddingbottom](img/b9c53cdb5290097212750e197c7226f3.png)

*   **percentage:** This type of value is used to specify the bottom padding in percent of the width of the element. It must be non-negative.

    **语法:**

    ```html
    padding-bottom: percentage;
    ```

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>CSS padding-bottom Property</title>

            <style>
                p.geek {
                padding-bottom: 10%;
                color: white;
                background: green;
                }
            </style>
        </head>

        <body style = "text-align: center;">

            <h1 style = "color: green;">GeeksforGeeks</h1>

            <h2>padding-bottom Property</h2>

            <!-- Below Paragraph element has a 
                padding-bottom of 10% -->
            <p class="geek">
                This paragraph has a padding-bottom: 10%;
            </p>
        </body>
    </html>                                        
    ```

    **输出:**
    ![paddingbottom](img/10cbdea1c8ad5fc75bcb126872cf6b75.png)

**支持的浏览器:***填充底部属性*支持的浏览器如下:

*   谷歌 Chrome 1.0
*   Internet Explorer 4.0
*   Firefox 1.0
*   歌剧 3.5
*   苹果 Safari 1.0