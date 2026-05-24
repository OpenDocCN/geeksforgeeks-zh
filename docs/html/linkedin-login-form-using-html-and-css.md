# 使用 HTML 和 CSS 的 LinkedIn 登录表单

> 原文:[https://www . geesforgeks . org/LinkedIn-log in-form-use-html-and-CSS/](https://www.geeksforgeeks.org/linkedin-login-form-using-html-and-css/)

如今，一个专业网站 LinkedIn 非常受欢迎。这个 UI 一般在“领英”网站上看到过。在本文中，我们将使用 HTML 和 CSS 创建一个 LinkedIn 登录 UI。下面是如何做的两个步骤。参考这篇文章，这将帮助初学者使用 HTML 和 CSS 构建一些令人敬畏的用户界面。

在代码之前，您只需要在程序中为图标包含以下样式表:

```html
https://use.fontawesome.com/releases/v5.7.0/css/all.css
```

**示例:**我们来看看如何用 likedin 这样的形式创建 sign。

## 【index.html】

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="description" content="Free Web tutorials" />
    <meta name="keywords" content="HTML, CSS, JavaScript" />
    <meta name="author" content="John Doe" />
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0" />
    <title>LinkedIn Login Form Using HTML and CSS</title>

    <!--Font Awesome-->
    <link rel="stylesheet" href=
        "https://use.fontawesome.com/releases/v5.7.0/css/all.css"
        integrity=
"sha384-lZN37f5QGtY3VHgisS14W3ExzMWZxybE1SJSEsQp9S+oqd12jhcu+A56Ebc1zFSJ" 
        crossorigin="anonymous" />

    <!--Style CSS-->
    <link rel="stylesheet" href="style.css" />

</head>

<body>
    <div class="container">
        <h2>Linked<span>
            <i class="fab fa-linkedin"></i>
        </span></h2>
        <div class="text">
            <h1>Sign in</h1>
            <p>Stay updated on your professional world</p>
        </div>
        <div class="your-input">
            <div class="input">
                <input type="text" name="email" 
                    id="email" required />
                <label for="email">Email</label>
            </div>
            <div class="input">
                <input type="password" name="password" 
                    id="password" required />
                <label for="password">
                    Password
                </label>
            </div>
        </div>
        <a href="#" class="forgot-password-link">
            Forgot Password?
        </a>
        <button>Sign in</button>
        <p class="join-link">
            New to linkedin?
            <a href="#" class="join-now">
                Join now
            </a>
        </p>
    </div>
</body>

</html>
```