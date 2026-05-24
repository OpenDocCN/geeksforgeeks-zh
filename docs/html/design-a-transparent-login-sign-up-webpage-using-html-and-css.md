# 使用 HTML 和 CSS 设计一个透明的登录/注册网页

> 原文:[https://www . geesforgeks . org/design-a-transparent-log in-sign-up-网页-使用-html-and-css/](https://www.geeksforgeeks.org/design-a-transparent-login-sign-up-webpage-using-html-and-css/)

**项目介绍:**

在本文中，我们将讨论如何使用 HTML 和 CSS 设计一个透明的登录网页。

**项目结构:**

> *   **指标。html**
> *   **什么事. CSS〔T7〕t8〔T9〕t1〕**

index.html

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <meta
            name="viewport"
            content="width=device-width, 
                     initial-scale=1.0"
        />
        <script src="https://kit.fontawesome.com/5845bc1bb6.js"
                crossorigin="anonymous"></script>
        <link href=
"https://fonts.googleapis.com/css2?family=Baloo+Bhai+2:wght@600&display=swap" 
              rel="stylesheet" />
        <link rel="stylesheet" href="style.css" />
        <title>Transparent Login Page using HTML/CSS</title>
    </head>

    <body>
        <div class="container">
            <div class="row1">
                <h1>LogIn</h1>
                <div class="row">
                    <i class="fas fa-envelope-square"></i>
                    <input type="email" name="Email" 
                           placeholder="Enter your email" />
                </div>
                <div class="row">
                    <i class="fas fa-key"></i>
                    <input type="password" name="pass" 
                           placeholder="Enter your password" />
                </div>
                <button class="btn">Submit</button>
            </div>
        </div>
    </body>
</html>
```