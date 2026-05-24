# 如何使用 Bootstrap 将图片放入没有空间的盒子里？

> 原文:[https://www . geeksforgeeks . org/如何在不使用空间的情况下将图像放入盒中-bootstrap/](https://www.geeksforgeeks.org/how-to-put-images-in-a-box-without-space-using-bootstrap/)

Bootstrap 4 是一个 CSS，一个由 Twitter 开发的前端网络开发库，它帮助开发者美化网页的外观。引导库有预定义的易于使用的 CSS 类，它帮助开发人员以最小的努力为网站提供艺术外观。

下面一行显示了在网页中插入简单图像的语法

```html
<img src="image-path" alt="Show this text if image does not appear" />
```

解决这个问题其实有三种方法。我将在这里提供所有三种解决方案。

1.  通过为图像提供边框。因此，它使图像出现在盒子里面。
2.  通过使用自定义 css 在具有边框属性的 div 中插入图像。
3.  通过使用自举。

让我们看看上述方法的演示。

1.  **By providing a border to the image.**

    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta http-equiv="X-UA-Compatible" content="ie=edge">
        <title>Bootstrap - Image inside Box</title>
    </head>
    <!-- Custom css to provide border to the image -->
    <style>
        img{
            border:5px solid green; 
         /* This line gives a green border of 5 pixels
              width to all images on the webpage. */ 
            This line does not cause any space 
            between the image and the border. */
        }
    </style>
    <body>
            <h2>
                Putting image inside a Box
            </h2>
    <!-- Put the path of image in the src of image tag. -->
            <img src="..." alt="Image Loading Failed" />    
    </body>
    </html>
    ```

    **输出:**
    ![Image with Border](img/0f594fb24eae91d2c4e452c84d454967.png)

2.  **By using custom css**

    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta http-equiv="X-UA-Compatible" content="ie=edge">
        <title>Bootstrap - Image inside Box</title>
    </head>
       <!-- Custom css to provide border to the div -->
    <style>
        /* 
        border class is used to give border to the div tag.
         */
       .border{
           border:5px solid green;
           /* green border of 5 pixels width */
           padding:0;
           /* padding to remove the space
           between inner components of the div*/
           max-width: fit-content;
           /*
            making the div take the 
            size of the image
            */
           }
        img{
            display: block;
            /* to make the image occupy 
            the whole container */
        }

    </style>
    <body>   
            <h2>
                Putting image inside a Box
            </h2>
            <!-- Enclosing the image tag inside the div
                having border class. 
            -->
            <div class="border">
                <img src="..." alt="Image Loading Failed" />
            </div>

    </body>
    </html>
    ```

    **输出:**
    ![](img/5f4c1da2e22e31b1f04e1eb0a8a2d475.png)

3.  Using bootstrap 4 css: We will be using the pre-defined class known as **cards** to make image appear inside a box.

    ```html
    <!DOCTYPE html>
    <html lang="en">

    <head>
        <meta charset="UTF-8">
        <meta name="viewport" 
              content="width=device-width, initial-scale=1.0">
        <meta http-equiv="X-UA-Compatible" 
              content="ie=edge">
        <title>Bootstrap - Image inside Box</title>
        <link rel="stylesheet"
              href=
    "https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/4.4.1/css/bootstrap.css" 
              integrity=
    "sha256-A47OwxL/nAN0ydiDFTSGX7ftbfTJTKgiJ0zqCuTPDh4=" 
              crossorigin="anonymous" />
    </head>
    <style>
        .border {
            border: 5px solid green !important;
            /* Border of width 5 pixels green in color */
            width: fit-content;
            /* To make the image take whole space of container */
        }
    </style>

    <body>
        <!-- Providing necessary padding and margin -->
        <h2 class="mx-5 mt-5">
                Putting image inside a Box
            </h2>
        <!-- using card class to place image inside a box -->
        <!-- Added custom css class border for additional properties -->
        <!-- Added necessary padding and margin classes -->
        <div class="card mx-5 px-0 py-0 border">
            <!-- Added card-img-top class to show 
                 the image on the top of the card. -->
            <!-- Since the image is the only content in card -->
            <!-- Image appears to be taking the whole card. -->
            <img src="..." alt="Image Loading Failed" class="card-img-top" />
        </div>

    </body>

    </html>
    ```

    **输出:**
    ![](img/30db6711f591e99f4f96aceffac48469.png)