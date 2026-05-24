# 如何检查推特引导加载与否？

> 原文:[https://www . geesforgeks . org/如何检查-Twitter-bootstrap-是加载还是不加载/](https://www.geeksforgeeks.org/how-to-check-twitter-bootstrap-is-loaded-or-not/)

**[【Bootstrap】](https://www.geeksforgeeks.org/bootstrap-tutorials/)**是一个非常有用的框架，由 Twitter 提供，让网站完全响应。它提供了预定义的 CSS 类，通常意味着无需任何更改就可以直接使用。要将 Bootstrap 加载到您的网站，请阅读本文 [**简介和安装**](https://www.geeksforgeeks.org/beginning-bootstrap-part-1/) 。

理解为什么我们需要检查引导是否已经通过 CDN 加载是非常重要的。如果将来某个时候 CDN 出现了一些问题，那么通过实现这个工具，您的网站将能够恢复到 Bootstrap 的本地版本。有 CDN 有很多优点，比如缓存内容，可以提高网站性能，所以不应该从你的网站上完全删除。为了检查 Bootstrap 是否已经加载，我们将使用[](https://www.geeksforgeeks.org/jquery-tutorials/)**和 [**模态**](https://www.geeksforgeeks.org/bootstrap-4-modal/) (这由 Bootstrap 提供)。在开始之前，了解**模式**很重要。模态是可以覆盖在文档上的元素。对话框是模态的一个例子。当模态元素被激活时，窗口的其余部分是不活动的。我们可以检查特定于 Bootstrap 的方法是否可用。**

****语法:****

```html
var bootstrap = (typeof $()."Bootstrap-specific method" == 'function');
```

****示例:**在本例中，我们将检查引导模式。如果引导已经加载，那么模式将被定义。如果模式是未定义的，那么我们将成功地返回到引导的本地版本。这个例子将说明使用 jQuery 和 modals 来验证引导是否已经加载。**

*   ****程序:**

    ```html
    <!DOCTYPE html>
    <html lang="en">

    <head>
        <title>
            Check twitter Bootstrap is loaded or not
        </title>
        <meta charset="utf-8">
        <meta name="viewport" 
              content="width=device-width, initial-scale=1">
        <link rel="stylesheet" href=
    "https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">

        <script src=
    "https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
        </script>

        <script src=
    "https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js">
        </script>

        <script src=
    "https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js">
        </script>

        <style>
            .disabled {
                pointer-events: auto !important;
            }
        </style>
    </head>

    <body>
        <center>
            <h1 class="text-success">GeeksforGeeks</h1>
            <b>A Computer Science Portal for Geeks</b>
        </center>
        <script>
        if (!$.fn.modal) {
            alert('CDN Bootstrap is not working');

            // Replace your_path with path where
            // local bootstrap is stored
            document.write('<script src=
    "Your_path_locall_one/bootstrap.min.js"></scr+ipt>');
            document.write('<link href=
    "Your_path_locall_one/bootstrap.min.css" rel="stylesheet">')
        } else {
            alert('CDN Bootstrap is loaded');
        }
        </script>
    </body>

    </html>
    ```** 
*   ****输出:**
    ![](img/411ffb5129db714ead0a98cdcf407007.png)**

****注意:**bootstrap 指定的方法可以是任何模态的，只要你需要仔细检查。**