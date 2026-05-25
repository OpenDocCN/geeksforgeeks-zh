# 如何使用放大镜弹出 jQuery 插件？

> 原文：[https://www.geeksforgeeks.org/how-to-use-the-magnific-popup-jquery-plugin/](https://www.geeksforgeeks.org/how-to-use-the-magnific-popup-jquery-plugin/)

放大镜弹出是一个快速，轻，移动友好和响应灯箱和模态对话框 jQuery 插件。它可以用来打开内联 HTML、ajax 加载的内容、图像、表单、iframe (YouTube 视频、Vimeo、谷歌地图)和照片库。它添加了使用 CSS3 过渡的动画效果。

## 安装过程

有几种方法可以开始使用这个插件：

*   从[这里](https://plugins.jquery.com/magnific-popup/)下载压缩文件夹的最新版本。
*   或者，通过在 Git Bash 中执行以下命令，将 [github 仓库](https://github.com/dimsemenov/Magnific-Popup.git)克隆到任何所需位置。

```bash
git clone https://github.com/dimsemenov/Magnific-Popup.git
```

*   因为放大镜是 jQuery 框架的一个插件，所以有必要引用 jQuery 库。这可以通过使用 Google 托管的 jQuery 版本或下载并使用发行版文件来实现。
*   **包含 CSS：** 添加放大镜的 `dist` 文件夹中的 `magnific-popup.css` 文件。

```html
<link rel="stylesheet" type="text/css" href="path/magnific-popup.css">
```

*   **包含 JavaScript：** 添加放大镜的 `dist` 文件夹中的 `jquery.magnific-popup.min.js` 文件。

```html
<script type="text/javascript" src="path/jquery.magnific-popup.min.js"></script>
```

## 示例 1

该示例显示了使用插件的弹出窗口。

### HTML

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