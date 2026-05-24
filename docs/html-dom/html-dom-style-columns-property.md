# HTML | DOM 样式列属性

> 原文:[https://www . geesforgeks . org/html-DOM-style-columns-property/](https://www.geeksforgeeks.org/html-dom-style-columns-property/)

HTML strong DOM Style 列属性用于设置列的宽度&列数。

**语法:**

*   **返回列属性:**

    ```html
    object.style.columns
    ```

*   **To Set the column property:**

    ```html
    object.style.columns= "auto|columnwidth columncount|
    initial|inherit"
    ```

    **属性值:**

    *   **自动:**将宽度&计数的两个值都设置为自动，即默认值(0)。
    *   **列宽:**设置列宽。
    *   **列数:**设置列数。
    *   **初始值:**设置默认值。
    *   **inherit:** 它从其父元素继承值。

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>
    <head>
        <title>
          HTML | DOM Style columns Property
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

                // Set column width and count.
                document.getElementById(
                  "example").style.columns = "200px 2";

                // Code for Firefox 
                document.getElementById(
                  "example").style.MozColumns = "200px 2";

            }
        </script>

    </body>

    </html>
    ```

    **输出:**

    *   **点击按钮前:**
        ![](img/99a2c2fdca24ebcdf176df1622a06d4c.png)
    *   **点击按钮后:**
        ![](img/4f37fb66b13638d56b943d36f429a4e4.png)

    **支持的浏览器:**以下列出了 *HTML | DOM Style 栏目属性*支持的浏览器:

    *   铬
    *   微软公司出品的 web 浏览器
    *   旅行队
    *   歌剧