# jQuery |闪烁板插件

> 原文:[https://www.geeksforgeeks.org/jquery-flickerplate-plugin/](https://www.geeksforgeeks.org/jquery-flickerplate-plugin/)

jQuery 提供了**闪烁板**插件，帮助我们的程序员为网站创建滑块，这些滑块可以在背景图像列表以及点导航功能和动画箭头之间循环。该插件由更多负责触摸检测和事件的库组成，例如定制的 **Modernizr** 和 jQuery **Finger** 库。在这个插件的帮助下，程序员可以在现代应用程序中创建和设计有效的滑块，可以轻松浏览网页内容。

**注意:**请将 jQuery [闪烁板插件](https://github.com/amilajack/Flickerplate)下载到你的工作文件夹中，并在你的代码头部分包含所需的文件，如下所示。

**包含闪烁板插件所需的文件:**

> <link href="”flickerplate.css”" rel="”stylesheet”" type="”text/css”/">
> <脚本 src=【闪烁板】></脚本>
> 
> <脚本 src = " modernizr-custom-v 2 . 7 . 1 . min . js "></脚本>
> <脚本 src = " jquery-finger-v 0 . 1 . 0 . min . js "></脚本>

**示例 1:****闪烁板**插件由 javascript 执行，它可以通过包含为用户界面设计的一类 HTML 代码来使用。下面的示例代码演示了插件的**闪烁()**函数的简单调用。

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1">

    <title>jQuery Flickerplate Plugin </title>

    <style>
        html {
            font-family: Arial, Helvetica, sans-serif;
            background-color: #ffffff;
            font-weight: 200;
        }

        body {
            margin: 0px;
            top: 0px;
            padding: 0px;
            bottom: 0px;
        }
    </style>

    <!--Required javascript-->
    <script src="jquery-v1.10.2.min.js" 
            type="text/javascript">
    </script>

    <script src="modernizr-custom-v2.7.1.min.js" 
            type="text/javascript">
    </script>

    <script src="jquery-finger-v0.1.0.min.js" 
            type="text/javascript">
    </script>

    <!--Include flickerpate files-->
    <link href="flickerplate.css" 
            type="text/css" rel="stylesheet">

    <script src="flickerplate.min.js" 
            type="text/javascript">
    </script>

    <script>
        $(document).ready(function () {
            $('.flicker-example').flicker();
        });
    </script>
</head>

<body>
    <div class="flicker-example" data-block-text="false">
        <ul>
            <li data-background="images/bgImage3.jpg">
                <div class="flick-title" style="color:black">
                    Write from home
                </div>
                <div class="flick-sub-text" style="color:black">
                    When the whole nation is on the verge of
                    lockdown due to COVID-19 pandemic and all
                    Geeks across the country have to stay 
                    indoors,how would it be if you can use
                    this free time to sharpen your skills?
                </div>
            </li>

            <li data-background="images/bgImage1.jpg">
                <div class="flick-title" style="color:black">
                    Get your dream job
                </div>
                <div class="flick-sub-text" style="color:black">
                    As the placement season is back so are we
                    to help you ace the interview. We have 
                    selected some most commonly asked and 
                    must do practice problems for you.
                </div>
            </li>

            <li data-background="images/bgImage2.jpg">
                <div class="flick-title" style="color:#000000">
                    Must do coding questions
                </div>
                <div class="flick-sub-text" style="color:#000000">
                    We have selected some most commonly asked
                    and must do practice problems for you. You 
                    can also take part in our mock placement 
                    contests which will help you learn different
                    topics and practice at the same time, 
                    simulating the feeling of a real placement 
                    test environment.
                </div>
            </li>
        </ul>
    </div>
</body>

</html>
```

**注意:**在上面的 HTML 代码中，*数据-块-文本*设置为“假”，去掉程序员提供的标题和子文本周围的框块。

**输出:**
![](img/b94500e0e2cacc3823670408947b304b.png "Simple Flickerplate Output")

**示例 2:****闪烁板**插件很容易配置，可以通过不同的方式完成，例如在 jQuery 代码中设置选项，或者在页面的实际元素上设置数据属性。在下面的示例中，请注意脚本部分中设置的选项和编写的注释。用户可以通过将其与下面给出的输出图像相关联来理解。

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1">

    <title>jQuery Flickerplate Plugin </title>

    <style>
        html {
            font-family: Arial, Helvetica, sans-serif;
            background-color: #ffffff;
            font-weight: 200;
        }

        body {
            margin: 0px;
            top: 0px;
            padding: 0px;
            bottom: 0px;
        }
    </style>

    <!--Required javascript-->
    <script src="jquery-v1.10.2.min.js" 
        type="text/javascript">
    </script>

    <script src="modernizr-custom-v2.7.1.min.js" 
        type="text/javascript">
    </script>

    <script src="jquery-finger-v0.1.0.min.js" 
        type="text/javascript">
    </script>

    <!--Include flickerpate files-->
    <link href="flickerplate.css" type="text/css"
                             rel="stylesheet" />

    <script src="flickerplate.min.js" 
        type="text/javascript">
    </script>
    <!--To make flicker touch enabled-->
    <script src="hammer-v2.0.3.min.js" 
        type="text/javascript">
    </script>

    <script>
        $(document).ready(function () {
            $('.flicker-example').flicker({

                // Traverse back and forth
                // between flicks
                arrows: true,

                // Set background colour to text
                block_text: true,

                // Set auto slide on load
                auto_flick: true,

                // Set time delay between 2 flicks
                auto_flick_delay: 2,

                // Pressing the next arrow will
                // get you to beginning
                arrowsConstraint: false,

                // Sets the starting flick
                // to 2nd navigation dot
                flick_position: 2,

                // Enable the dot navigation
                dot_navigation: true, 

                // Dot navigation is set in the left side
                dot_alignment: 'left',

                // Darkens the navigation dot
                theme: 'dark',

                // Set the type of animation
                flick_animation: 'transition-slide'
            });
        });
    </script>
</head>

<body>
    <div class="flicker-example" data-block-text="false">
        <ul>
            <li data-background="images/bgImage3.jpg">

                <div class="flick-title" style="color:black">
                    Write from home
                </div>
                <div class="flick-sub-text" style="color:black">
                    When the whole nation is on the verge of 
                    lockdown due to COVID-19 pandemic and all 
                    Geeks across the country have to stay indoors,
                    how would it be if you can use this free 
                    time to sharpen your skills?
                </div>
            </li>

            <li data-background="images/bgImage1.jpg">
                <div class="flick-title" style="color:black">
                    Get your dream job
                </div>
                <div class="flick-sub-text" style="color:black">
                    As the placement season is back so are we 
                    to help you ace the interview. We have 
                    selected some most commonly asked
                    and must do practice problems for you.
                </div>
            </li>

            <li data-background="images/bgImage2.jpg">
                <div class="flick-title" style="color:#000000">
                    Must do coding questions
                </div>
                <div class="flick-sub-text" style="color:#000000">
                    We have selected some most commonly asked
                    and must do practice problems for you. You 
                    can also take part in our mock placement
                    contests which will help you learn different 
                    topics and practice at the same time, 
                    simulating the feeling of a real placement 
                    test environment.
                </div>
            </li>
        </ul>
    </div>
</body>

</html>
```

**输出:**
![](img/3bf69e36437342ea3124dcf164d94251.png "flickerplate set options output")