# 使用 CSS 显示调整大小和裁剪后的图像

> 原文:[https://www . geesforgeks . org/display-a-调整大小和裁剪图像-使用-css/](https://www.geeksforgeeks.org/display-a-resized-and-cropped-image-using-css/)

它有助于为网页上的预定义位置动态调整和裁剪任何图像。调整大小和裁剪后的图像用于网页。有一种方法可以让我们在 div 中移动裁剪后的图像。

*   Regular width and height that squeeze the image to fit in that pre-defined position.
    **Example:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>

        <!-- Style to set the height and width
            of image -->
        <style>
            img {
                width:200px;
                height:120px;
                border:2px solid green;
            }
        </style>
    </head>

    <body style="text-align:center">

        <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20190306102929/1172.png">

    </body> 

    </html>                    
    ```

    **输出:**
    ![](img/b4085682439a858101aa9aaee3ce7765.png)

*   Regular width, height and background position using the image as a background image that fit in that pre-defined position (randomly cropped).
    **Example:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <style>
            div {
                background-image:url(
    'https://media.geeksforgeeks.org/wp-content/uploads/20190306102929/1172.png'); 
                width:200px; 
                height:120px; 
                background-position:center;
                border:2px solid green;
            }
        </style>
    </head>

    <body>
        <center>
            <div></div>
        </center>
    </body> 

    </html>                    
    ```

    **输出:**
    ![](img/5459915292fb64263c88dfc3704a6526.png)

*   It is the final procedure to cropped the image and also it can be resized. In this method we can move the image within the div. Use negative margin to move the image around within the div.

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <style>
            .crop {
                width: 200px;
                height: 120px;
                overflow: hidden;
                border:2px solid green;
            }
            .crop img {
                width: 450px;
                height: 300px;
                margin: -30px 0 0 -280px;
            } 
        </style>
    </head>

    <body>
        <center>
            <div class="crop">
                <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20190306102929/1172.png"
                alt="cropped image">
            </div>
        </center>
    </body>

    </html>                                   
    ```

    **输出:**
    ![](img/6567cc3e3477e3f8a14e3aaf055c7641.png)