# 如何使用 jQuery Plugin 为手机设计图片/视频的惰性加载？

> 原文:[https://www . geesforgeks . org/how-design-lazy-loading-images-video-for-mobile-use-jquery-plugin/](https://www.geeksforgeeks.org/how-to-design-lazy-loading-of-images-videos-for-mobiles-using-jquery-plugin/)

在本文中，我们将学习使用 jQuery Lazy Load XT 插件为面向移动的应用程序设计图像或视频的加载。

**先决条件:**从[链接](https://github.com/ressio/lazy-load-xt)下载预编译的所需库文件，并将其保存在您的工作文件夹中，以备后续实施。

**示例 1:** 以下示例演示了使用 HTML 和上面的 jQuery 插件进行图像的 ajax 加载。

## HTML

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8" />

        <meta
            name="viewport"
            content="width=device-width, initial-scale=1.0"/>
        <link href="bootstrap.min.css" rel="stylesheet" />
        <link rel="stylesheet" href="style.css" />
        <script src="jquery.js"></script>
        <script src="jquery.lazyloadxt.js"></script>
        <script>
            $(window).on("ajaxComplete", function () {
                setTimeout(function () {
                    $(window).lazyLoadXT();
                }, 50);
            });
        </script>
        <style>
            body {
                text-align: center;
            }
        </style>
    </head>
    <body>
        <div class="container">
            <div class="page-header">
                <p class="lead">Images loading using AJAX</p>

            </div>

<p>
                <a class="btn btn-primary btn-lg"
                   role="button"
                   href="#"
                   onclick="$('#divID').load('myajax.htm #divID');
                            return false;">
                    Reload
                </a>
            </p>

            <div id="divID">

<p><img data-src="images/geeksimage1.PNG" 
                        width="400" height="265" />
                </p>

<p><img data-src="images/gfg2.JPG" 
                        width="400" height="265" />
                </p>

<p><img data-src="images/gfg4.JPG" 
                        width="400" height="265" />
                </p>

<p><img data-src="images/gfg6.PNG" 
                        width="400" height="265" />
                </p>

<p><img data-src="images/background2.JPG"
                        width="400" height="265" />
                </p>

<p><img data-src="images/background3.JPG" 
                        width="400" height="265" />
                </p>

            </div>
        </div>
    </body>
</html>
```