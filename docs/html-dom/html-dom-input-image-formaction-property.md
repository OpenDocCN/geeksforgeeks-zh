# HTML | DOM 输入图像格式属性

> 原文:[https://www . geesforgeks . org/html-DOM-input-image-formaction-property/](https://www.geeksforgeeks.org/html-dom-input-image-formaction-property/)

HTML DOM 中的**输入图像格式属性**用于设置或返回输入图像的格式属性的值。提交表单后，会调用 formAction 属性。表单数据将在表单提交后发送到服务器。它覆盖了<表单>元素的动作属性的特征。

**语法:**

*   它返回 formAction 属性。

    ```html
    imageObject.formAction
    ```

*   它用于设置 formAction 属性。

    ```html
    imageObject.formAction = URL 
    ```

**属性值:**包含单值 URL，用于指定表单提交后要发送数据的文档的 URL。

**The possible value of URL are:**

*   **绝对 URL:** 它指向一个页面的完整地址。例如:www.geeksforgeeks.org/data-structure*   **relative URL:** It is used to point to a file within in a webpage. For Example: gfg.php

    **返回值:**返回一个代表表单网址的字符串值。

    **示例 1:** 本示例说明如何返回**表单**属性。

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            HTML DOM Input Image formAction
        </title>
    </head>

    <body style="text-align:center;">

        <h1 style="color:green;"> 
          GeeksforGeeks 
        </h1>

        <h4>
          DOM Input Image formAction Property</h4>
        <button onclick="my_geek()">
            <input id="myImage" type="image" formAction="test.php" src=
    "https://media.geeksforgeeks.org/wp-content/uploads/gfg-40.png" 
                   alt="Submit" width="48" height="48" formMethod="post" 
                   formNoValidate>
        </button>

        <h2 id="Geek_h" style="color:green;"></h2>
        <script>
            function my_geek() {

                // Return target, alt and height. 
                var txt = document.getElementById(
                    "myImage").formAction;
                document.getElementById(
                    "Geek_h").innerHTML = txt;
            }
        </script>
    </body>

    </html>
    ```

    **输出:**

    *   点击按钮前:
        ![](img/0c77c5e94971e440a076d9c46b13a0aa.png)
    *   点击按钮后:
        ![](img/67ed797430c0449775f5c093fc24f337.png)

    **例 2:** 本例说明如何设置**形态**属性。

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            HTML DOM Input Image formAction
        </title>
    </head>

    <body style="text-align:center;">

        <h1 style="color:green;"> 
         GeeksforGeeks 
        </h1>

        <h4>
         DOM Input Image formAction Property
        </h4>
        <button onclick="my_geek()">
            <input id="myImage" type="image" formAction="test.php" src=
    "https://media.geeksforgeeks.org/wp-content/uploads/gfg-40.png" 
                   alt="Submit" width="48" height="48" formMethod="post" 
                   formNoValidate>
        </button>

        <h2 id="Geek_h" style="color:green;"></h2>
        <script>
            function my_geek() {

                // Return target, alt and height. 
                var txt = document.getElementById(
                    "myImage").formAction = "www.geeksforgeeks.org";
                document.getElementById(
                    "Geek_h").innerHTML = "The formAction was changed to "
                     + txt;
            }
        </script>
    </body>

    </html>
    ```

    **输出:**

    *   点击按钮前:
        ![](img/0c77c5e94971e440a076d9c46b13a0aa.png)
    *   点击按钮后:
        ![](img/9a6c46563c25d7d2447f51a6a6673b92.png)

    **支持的浏览器:***HTML DOM 输入图像格式属性*支持的浏览器如下:

    *   谷歌 Chrome
    *   微软公司出品的 web 浏览器
    *   火狐浏览器
    *   歌剧
    *   旅行队