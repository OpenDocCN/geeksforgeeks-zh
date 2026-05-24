# HTML | DOM 样式列填充属性

> 原文:[https://www . geesforgeks . org/html-DOM-style-column fill-property/](https://www.geeksforgeeks.org/html-dom-style-columnfill-property/)

HTML strong DOM Style columnFill 属性指定如何填充一列(平衡或不平衡)。
**语法:**

*   获取列填充属性

    ```html
    object.style.columnFill

    ```

    *   To set the columnFill property

    ```html
    object.style.columnFill= "balance|initial|auto|inherit"
    ```

    **属性值:**

    *   **余额:**平衡列(默认)。*   **自动:**列将有不同的长度&依次填充。*   **初始值:**设置默认值。*   **inherit:** Inherit value from parent.

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>
    <head>
        <title>
          HTML | DOM Style columnFill Property
        </title>
    </head>
    <body>

        <div id="example">
          GEEKSFORGEEKS welcomes you to the learning portal.
          GEEKSFORGEEKS welcomes you to the learning portal. 
          GEEKSFORGEEKS welcomes you to the learning portal.
          GEEKSFORGEEKS welcomes you to the learning portal. 
          GEEKSFORGEEKS welcomes you to the learning portal.
          GEEKSFORGEEKS welcomes you to the learning portal.
          GEEKSFORGEEKS welcomes you to the learning portal. 
          GEEKSFORGEEKS welcomes you to the learning portal.
          GEEKSFORGEEKS welcomes you to the learning portal. 
          GEEKSFORGEEKS welcomes you to the learning portal.
          GEEKSFORGEEKS welcomes you to the learning portal.
          GEEKSFORGEEKS welcomes you to the learning portal. 
          GEEKSFORGEEKS welcomes you to the learning portal. 
          GEEKSFORGEEKS welcomes you to the learning portal.
          GEEKSFORGEEKS welcomes you to the learning portal.
          GEEKSFORGEEKS welcomes you to the learning portal.

        </div>
        <button onclick="split()">click</button>

        <script>
            function split() {

                document.getElementById(
                  "example").style.columnFill = "auto";
            }
        </script>

    </body>

    </html>
    ```

    **注:****13.0-moz-**支持 **CCSS3 填列属性**。

    **支持的浏览器:**主要浏览器不支持*HTML | DOM Style column fill Property*。