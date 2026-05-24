# Firebase 与 Web 的集成

> 原文: [https://www.geeksforgeeks.org/firebase-integration-with-web/](https://www.geeksforgeeks.org/firebase-integration-with-web/)

Firebase 是谷歌开发的一个平台，用于创建移动和网络应用程序。我们将看到如何将 firebase 与我们的示例 Web 应用程序集成或连接起来。

**方法:** 按照以下步骤将您的网络应用程序与 firebase 集成。

*   首先，我们将在 `index.html` 文件中创建一个 HTML 页面。
*   创建 HTML 页面后，我们将创建一个名为 `form.js` 的页面。
*   JavaScript 文件创建后，登录 `firebase console` 并创建一个新项目。
*   添加任何您选择的名称。完成后，转到 `authentication => login method`。
*   现在点击 `Enable E-mail/Password`。
*   完成此步骤后，运行 HTML 文件。

下图是上述方法的实施

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0" />

<script src=
"https://www.gstatic.com/firebasejs/8.2.7/firebase-app.js">
    </script>

<script src=
"https://www.gstatic.com/firebasejs/8.2.7/firebase-auth.js">
    </script>

<script src="form.js"></script>
    <title>Login System</title>
</head>

<body>
    <div class="formContainer">
        <h1>Enter Credentials Here:</h1>
        <input type="email" 
            placeholder="email here" id="email" />
        <br />
        <input type="password" 
            placeholder="password here" id="password" />
        <br />
        <button onclick="signUp()" id="signUp">
            SignUp
        </button>
        <button onclick="signIn()" id="signIp">
            SignIn
        </button>
        <button onclick="signOut()" id="signOut">
            SignOut
        </button>
    </div>
</body>

</html>
```