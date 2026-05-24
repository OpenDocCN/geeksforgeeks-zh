# 如何使用放大镜弹出 jQuery 插件？

> 原文:[https://www . geesforgeks . org/如何使用-放大镜-弹出-jquery-plugin/](https://www.geeksforgeeks.org/how-to-use-the-magnific-popup-jquery-plugin/)

放大镜弹出是一个快速，轻，移动友好和响应灯箱和模态对话框 jQuery 插件。它可以用来打开内联 HTML、ajax 加载的内容、图像、表单、iframe (YouTube 视频、Vimeo、谷歌地图)和照片库。它添加了使用 CSS3 过渡的动画效果。

**安装过程:**有几种方法可以开始使用这个插件:

*   Download the latest version of the compressed folder of the magnifying glass pop-up window from [here](https://plugins.jquery.com/magnific-popup/) .
*   Or, clone the [github repository](https://github.com/dimsemenov/Magnific-Popup.git) to any desired location by executing the following command in Git Bash.

    ```html
    git clone https://github.com/dimsemenov/Magnific-Popup.git
    ```

*   Because magnifying glass is a plug-in of jQuery framework, it is necessary to refer to jQuery library. This can be achieved by using the version of jQuery hosted by Google or downloading and using distribution files.
*   **Contains CSS:** Add the **magnifying glass -popup.css** file from the dist folder of magnifying glass.

    ```html
    <link rel="stylesheet" type="text/css" href="path/magnific-popup.css">
    ```

*   **Include JavaScript:** Add **jquery. Magnifier -popup.min.js** file from dist folder of magnifying glass.

    ```html
    <script type="text/javascript" src="path/jquery.magnific-popup.min.js"></script>
    ```

**示例 1:** 该示例显示了使用插件的弹出窗口。

## html

```html
<!DOCTYPE html>
<html>

<head>

    <!-- Include CSS of Magnific Popup -->
    <link rel="stylesheet" type="text/css"
            href="css/magnific-popup.css">
</head>

<body style="text-align:center;">
    <!-- Button to open popup -->
    <button>
        <a href="#popup-info" class="open-popup"
            style="text-decoration: none;">
            Click to Open PopUp
        </a>
    </button>
    <!-- Popup to display -->
    <div id="popup-info" class="mfp-hide" style=
            "text-align:center;
            background:white;height:600px;">

        <h1 style="color: green;">
            GEEKSFORGEEKS
        </h1>

        <div style="font-size: 15px; 
            font-weight: bold;">
            WELCOME TO GEEKSFORGEEKS
        </div>
    </div>

    <!-- Include jQuery -->
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js">
    </script>

    <!-- Include the Magnific Popup JavaScript -->
    <script type="text/javascript" 
src="js/jquery.magnific-popup.min.js">
    </script>

    <script type="text/javascript">

        $(document).ready(function ($) {
            $('.open-popup').magnificPopup({
                type: 'inline',

                // Fixed position will be used
                fixContentPos: true,

                // Since disabled, Magnific Popup
                // will not put close button
                // inside content of popup
                closeBtnInside: false,
                preloader: false,

                // Delay in milliseconds before
                // popup is removed
                removalDelay: 160,

                // Class that is added to
                // popup wrapper and background
                mainClass: 'mfp-fade'
            });
        });
    </script>
</body>

</html>
```