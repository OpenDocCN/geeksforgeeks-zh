# 如何使用 CSS 自动调整图像大小以适合 div 容器？

> 原文:[https://www . geesforgeks . org/如何使用-css/](https://www.geeksforgeeks.org/how-to-auto-resize-an-image-to-fit-a-div-container-using-css/) 自动调整图像大小以适合容器

若要自动调整图像或视频的大小以适合 div 容器，请使用 object-fit 属性。它用于指定图像或视频如何适合容器。

**对象适配属性:**该属性用于指定图像或视频如何调整容器的大小和适配容器。它告诉内容如何以各种方式适合特定的 div 容器，例如保持长宽比或者尽可能地扩大和占据空间。

*   **Example 1:** This example describes the auto-resize image fit to div container. This example does not contain object-fit property.

    ```html
    <!DOCTYPE html> 
    <html> 
        <head> 
            <style>
                .geeks {
                    width:60%;
                    height:300px;
                }
                img {
                    width:100%;
                    height:100%;
                }
            </style>
        </head> 
        <body>
            <div class = "geeks">
                <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-25.png" 
            alt = "Geeks Image" />
            </div>
        </body> 
    </html>                    
    ```

    **输出:**
    ![](img/fc3859804a2085e57f14cdee84fad2b5.png)
    在上例中由于没有使用 object-fit 属性，图像被挤压以适合容器，其原始纵横比被破坏。

*   **Example 2:** This example is used to display the part of image when use resize the div container.

    ```html
    <!DOCTYPE html> 
    <html> 
        <head> 
            <style>
                .geeks {
                    width:60%;
                    height:300px;
                }
                img {
                    width:100%;
                    height:100%;
                    object-fit:cover;
                }
            </style>
        </head> 
        <body>
            <div class = "geeks">
                <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-25.png" 
                alt = "Geeks Image" />
            </div>
        </body> 
    </html>                    
    ```

    **输出:**
    ![](img/fb450765958d804aca064e47ef76308e.png)
    **注:**:使用*对象-配合:覆盖；*将图像的边切掉，保留长宽比，同时也填充空间。

*   **Example 3:** This example displays an image without using object-fit property. In this example, the size of the image is set manually and the image will not be able to maintain it’s aspect ratio and adjust or resize according to div container on resizing the browser window.

    ```html
    <!DOCTYPE html> 
    <html> 
    <head> 
        <style>
            body {
                text-align:center;
            } 
            img {
                width:400px;
                height:200px;
            }
        </style> 
    </head> 
    <body>
        <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-25.png" 
        alt="Geeks Image">
    </body> 
    </html>                    
    ```

    **输出:**
    ![](img/cce5b3f86f5d5bd8b49f3d93bdf27be9.png)

*   **Example 4:** This example display the part of image or image using object-fit property. In this example, the size of the image is set manually and the object-fit property is also used. In this case, on resizing the browser the image will maintain it’s aspect ratio and will not be resized according to div container.

    ```html
    <!DOCTYPE html> 
    <html> 
        <head> 
            <style>
                body {
                    text-align:center;
                } 
                img {
                    width:400px;
                    height:200px;
                    object-fit: cover;
                }
            </style> 
        </head> 
        <body>
            <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-25.png"
            alt="Geeks Image">
        </body> 
    </html>                    
    ```

    **输出:**
    ![](img/b772115e46b8344bbdf7ce5e138ead99.png)

    **注:**属性*对象适配:封面；*将切割图像的侧面，保留纵横比，同时填充空间。

HTML 是网页的基础，通过构建网站和网络应用程序用于网页开发。您可以通过以下 [HTML 教程](https://www.geeksforgeeks.org/html-tutorials/)和 [HTML 示例](https://www.geeksforgeeks.org/html-examples/)从头开始学习 HTML。

CSS 是网页的基础，通过设计网站和网络应用程序用于网页开发。你可以通过以下 [CSS 教程](https://www.geeksforgeeks.org/css-tutorials/)和 [CSS 示例](https://www.geeksforgeeks.org/css-examples/)从头开始学习 CSS。