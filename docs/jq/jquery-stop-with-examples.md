# jQuery | stop()带示例

> 原文:[https://www.geeksforgeeks.org/jquery-stop-with-examples/](https://www.geeksforgeeks.org/jquery-stop-with-examples/)

stop()方法是 jQuery 中的一个内置方法，用于停止所选元素当前正在运行的动画。

**语法:**

```html
$(selector).stop(stopAll, goToEnd);
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **stopAll:** 为可选参数，该参数值为布尔值。此参数还用于指定是否停止排队的动画。此参数的默认值为 false。
*   **goToEnd:** 为可选参数，该参数值为布尔值。此参数用于指定是否立即完成所有动画。此参数的默认值为 false。

**返回值:**此方法返回应用了停止方法的选定元素。

以下示例说明了 jQuery 中的 stop()方法:

**例 1:** 本例不包含任何参数。

```html
<!DOCTYPE html>
<html>
    <head>
        <title>The stop Method</title>
        <script src=
        "https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
        </script>

        <!-- jQuery code to show the working of this method -->
        <script>
            $(document).ready(function() {
                $("#gfg_start").click(function() {
                    $("div").animate({
                        height: 300
                    }, 1000);
                    $("div").animate({
                        width: 300
                    }, 1000);
                });
                $("#gfg_stop").click(function() {
                    $("div").stop();
                });
            });
        </script>
        <style>
            div {
                background: green;
                height: 60px;
                width: 60px;
            }
            button {
                margin-bottom:30px;
            }
        </style>
    </head>
    <body>
        <!-- click on this button and animation will start -->
        <button id="gfg_start">Start</button>
        <!-- click on this button and animation will stop -->
        <button id="gfg_stop">Stop</button>
        <div></div>
    </body>
</html>
```

**输出:**

<video class="wp-video-shortcode" id="video-229377-1" width="510" height="354" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20180921_225755.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20180921_225755.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20180921_225755.mp4)</video>

**例 2:** 本例包含参数。

```html
<!DOCTYPE html>
<html>
    <head>
        <title> The stop Method</title>
        <script src=
        "https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
        </script>

        <script>
            $(document).ready(function() {
                var div = $("div");
                $("#start").click(function() {
                    div.animate({
                        height: 280
                    }, "slow");
                    div.animate({
                        width: 280
                    }, "slow");
                    div.animate({
                        height: 120
                    }, "slow");
                    div.animate({
                        width: 120
                    }, "slow");
                });
                $("#stop").click(function() {
                    div.stop(true, true);
                });
            });
        </script>
        <style>
            div {
                background: green;
                height: 100px;
                width: 100px;
            }
            button {
                margin-bottom:30px;
            }
        </style>
    </head>
    <body>
        <!-- click on this button and animation will start -->
        <button id="start">Start </button>
        <!-- click on this button and animation will stop -->
        <button id="stop">Stop </button>
        <div></div>
    </body>
</html>
```

**输出:**

<video class="wp-video-shortcode" id="video-229377-2" width="582" height="432" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20180921_230734.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20180921_230734.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20180921_230734.mp4)</video>