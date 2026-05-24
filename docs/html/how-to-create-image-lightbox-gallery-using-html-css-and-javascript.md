# 如何使用 HTML CSS 和 JavaScript 创建图像灯箱图库？

> 原文:[https://www . geesforgeks . org/how-create-image-light box-gallery-use-html-CSS-and-JavaScript/](https://www.geeksforgeeks.org/how-to-create-image-lightbox-gallery-using-html-css-and-javascript/)

![](img/576900b9ed4a9bc8b111c9965082aedb.png)

灯箱画廊基本上是用来查看画廊图像的细节。您可以编写 JavaScript 代码来实现这一点，但是我们也可以使用一些下载的 JS 和 CSS。在本文中，我们将下载灯箱，并将 JS 和 CSS 文件附加到我们的代码中。为了我们自己的设计满意，我们也可以随心所欲地使用 CSS 代码。我们将把这项任务分成三个部分。在第一部分中，我们将创建结构，在第二部分中，我们将为自己的目的添加一些 CSS。在最后一节，我们将链接下载的 JS snd CSS 文件。

我们必须下载灯箱，我们可以从链接下载:https://github.com/lokesh/lightbox2/releases

**创建结构:**在本节中，我们将只使用 HTML 进行编码，以创建一个普通的 HTML gallary。

*   **HTML code:**

    ## Hypertext markup language

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>Lightbox Gallery</title>
    </head>

    <body>
        <h2>GeeksforGeeks</h2>
        <b>A Computer Science Portal for Geeks</b>
        <div class="gallery">
            <a href=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200318142254/html9.png">
                <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200318143104/html10.png">
            </a>
            <a href=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200318142245/CSS8.png">
                <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200318143101/CSS9.png">
            </a>
            <a href=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200318142240/Bootstrap5.png">
                <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200318143058/Bootstrap6.png">
            </a>
            <a href=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200318142257/JavaScript2.png">
                <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200318143106/JavaScript3.png">
            </a>
            <a href=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200318142303/jquery.png">
                <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200318143108/jquery4.png">
            </a>
            <a href=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200318142309/php7.png">
                <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200318143112/php8.png">
            </a>
        </div>
    </body>

    </html>
    ```

**设计结构:**在本节中，我们将添加一些 CSS 属性，以使图像库具有吸引力。

*   **CSS 代码:**

    ## 半铸钢ˌ钢性铸铁(铸造半钢)

    ```html
    <style>
        body {
            text-align: center;
        }

        h2 {
            color: green;
        }

        .gallery {
            margin: 10px 40px;
        }

        .gallery img {
            width: 200px;
            height: 50px;
            transition: 1s;
            padding: 5px;
        }

        .gallery img:hover {
            filter: drop-shadow(4px 4px 6px gray);
            transform: scale(1.1);
        }
    </style>
    ```

**最终解决方案:**在本节中，您必须将下载的 CSS 和 JS 文件链接到您的代码中。您可以通过解压文件来链接下载的文件。对于 CSS 文件，使用带有 **href** 属性的 [<链接>](https://www.geeksforgeeks.org/html-link-tag/) 标签作为 CSS 的地址，对于 JS 文件，使用带有 **src** 属性的 [<脚本>](https://www.geeksforgeeks.org/html-script-tag/) 标签作为代码。最后我们要把**data-light box = " my gallery "**属性放在 [< a >](https://www.geeksforgeeks.org/html-a-tag/) 标签里面。“下一个”和“上一个”按钮将在 JS 文件附加过程中自动附加。

*   **Final Code:**

    ## Hypertext Markup Language

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>Lightbox Gallery</title>
        <link rel="stylesheet" 
              type="text/css" 
              href="lightbox2/dist/css/lightbox.min.css">
        <script src=
    "lightbox2/dist/js/lightbox-plus-jquery.min.js">
        </script>
        <style>
            body {
                text-align: center;
            }

            h2 {
                color: green;
            }

            .gallery {
                margin: 10px 40px;
            }

            .gallery img {
                width: 200px;
                height: 50px;
                transition: 1s;
                padding: 5px;
            }

            .gallery img:hover {
                filter: drop-shadow(4px 4px 6px gray);
                transform: scale(1.1);
            }
        </style>
    </head>

    <body>
        <h2>GeeksforGeeks</h2>
        <b>A Computer Science Portal for Geeks</b>
        <div class="gallery">
            <a href=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200318142254/html9.png"
               data-lightbox="mygallery">
                <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200318143104/html10.png">
            </a>
            <a href=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200318142245/CSS8.png" 
               data-lightbox="mygallery">
                <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200318143101/CSS9.png">
            </a>
            <a href=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200318142240/Bootstrap5.png"
               data-lightbox="mygallery">
                <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200318143058/Bootstrap6.png">
            </a>
            <a href=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200318142257/JavaScript2.png" 
               data-lightbox="mygallery">
                <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200318143106/JavaScript3.png">
            </a>
            <a href=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200318142303/jquery.png"
               data-lightbox="mygallery">
                <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200318143108/jquery4.png">
            </a>
            <a href=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200318142309/php7.png"
               data-lightbox="mygallery">
                <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200318143112/php8.png">
            </a>
        </div>
    </body>

    </html>
    ```

*   **Output:**

    ![](img/744464ced30fe8b7af413a1cee3fae12.png)