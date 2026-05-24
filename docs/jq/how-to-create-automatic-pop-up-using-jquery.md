# 如何使用 jQuery 创建自动弹出？

> 原文:[https://www . geesforgeks . org/如何创建-自动-弹出-使用-jquery/](https://www.geeksforgeeks.org/how-to-create-automatic-pop-up-using-jquery/)

在本文中，我们将向您展示如何为订阅任何服务制作一个自定义的自动弹出框。当您访问任何特定网站时，您可能经常会遇到一个弹出框，要求订阅任何服务。因此，在本文中，您将学习如何自定义弹出框并制作自己的弹出框。我们将使用简单的 HTML、CSS、Bootstrap 和 jQuery 代码来演示这个过程。

**说明:**

首先，我们需要创建一个**index.html**文件，并将下面的**index.html**文件的代码粘贴到其中。这个**index.html**文件包括了位于正文标签底部的 **app.js** 文件。现在在 **app.js** 文件中编写 jQuery ready 函数，该函数只在文档准备好的时候运行。之后是 3 秒后运行的 **setTimeout()** 功能，在该 **setTimeout()** 功能中，我们将弹出框显示为‘块’，这样 3 秒后就可以看到了。然后，我们在两个按钮上应用了 click 事件，只要有人点击它，弹出框的显示就会变成“无”。

**HTML 代码:**

## HTML

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <!-- Required meta tags -->
        <meta charset="utf-8" />
        <meta
            name="viewport"
            content="width=device-width,
      initial-scale=1, shrink-to-fit=no"
        />

        <!-- Bootstrap CSS -->
        <link rel="stylesheet"
              href=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css"
              integrity=
"sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm"
              crossorigin="anonymous" />

        <title>Automatic Pop-Up
      </title>
    </head>

    <body>
        <h1 class=
"text-center text-white mt-5 font-weight-bold">
            Automatic Pop-Up using jQuery
        </h1>
        <br />
        <br />
        <div class="POPmain"
             style="display: none;">
            <div id="popup">
                <input type="email"
                       class=
                  "text-center w-50 form-control mt-5"
                       id="emailId"
                       placeholder="type your email here..." />

                <button class=
"submitId btn btn-primary font-weight-bold mt-5">
                    Subscribe
                </button>
                <button class=
"submitId btn btn-primary text-center font-weight-bold mt-5">
                    No, Thanks
                </button>
            </div>
        </div>

        <!-- Optional JavaScript -->
        <!-- jQuery first, then Popper.js, then Bootstrap JS -->
        <script src=
 "https://code.jquery.com/jquery-3.2.1.slim.min.js"
                integrity=
 "sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN"
                crossorigin="anonymous"></script>

        <script src=
"https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.9/umd/popper.min.js"
                integrity=
"sha384-ApNbgh9B+Y1QKtv3Rn7W3mgPxhU9K/ScQsAP7hUibX39j7fakFPskvXusvfa0b4Q"
                crossorigin="anonymous"></script>

        <script src=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js"
                integrity=
"sha384-JZR6Spejh4U02d8jOt6vLEHfe/JQGiRRSQQxSfFWpi1MquVdAyjUar5+76PVCmYl"
                crossorigin="anonymous"></script>
    </body>
</html>
```