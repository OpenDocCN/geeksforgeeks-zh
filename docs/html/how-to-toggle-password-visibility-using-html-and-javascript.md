# 如何使用 HTML 和 JavaScript 切换密码可见性？

> 原文:[https://www . geesforgeks . org/如何切换-密码-可见性-使用-html-和-javascript/](https://www.geeksforgeeks.org/how-to-toggle-password-visibility-using-html-and-javascript/)

密码是那些显示为** * * * **的输入类型。它可以通过添加眼睛图标的特征向用户显示，以便用户可以看到密码。

**接近**

*   我们将显示两个图像图标“[eye.png](https://media.geeksforgeeks.org/wp-content/uploads/20210917145551/eye-300x240.png)”和“[eyeslash.png](https://media.geeksforgeeks.org/wp-content/uploads/20210917150049/eyeslash-300x240.png)的使用”
*   使用 JavaScript 切换这些图像。
*   我们将切换*密码*输入字段的 [*类型*](https://www.geeksforgeeks.org/html-input-typepassword/) (文本- >密码和密码- >文本)

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <h2 style="color:green">
        GeeksforGeeks
    </h2>

    <div class="col-sm-6">
        <form method="post" class="form-group ">
            Username
            <input type="text" name="username" 
                autofocus="" autocapitalize="none" 
                autocomplete="username" required=""
                id="id_username" class="form-control">

            Password
            <input type="password" name="password" 
                class="form-control" 
                autocomplete="current-password" required=""
                id="id_password">

            <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210917150049/eyeslash-300x240.png"
                width="1.8%" height="1%" 
                style="margin-left: -5%;display:inline;
                vertical-align: middle" 
                id="togglePassword">

            <button type="submit" class="btn btn-primary">
                Login
            </button>
        </form>
    </div>
</body>

<script>
    const togglePassword = 
        document.querySelector('#togglePassword');

    const password = document.querySelector('#id_password');

    togglePassword.addEventListener('click', function (e) {

        // Toggle the type attribute
        const type = password.getAttribute(
            'type') === 'password' ? 'text' : 'password';
        password.setAttribute('type', type);

        // Toggle the eye slash icon
        if (togglePassword.src.match(
"https://media.geeksforgeeks.org/wp-content/uploads/20210917150049/eyeslash.png")) {
            togglePassword.src =
"https://media.geeksforgeeks.org/wp-content/uploads/20210917145551/eye.png";
        } else {
            togglePassword.src =
"https://media.geeksforgeeks.org/wp-content/uploads/20210917150049/eyeslash.png";
        }
    });
</script>

</html>
```

**输出:**

![](img/c3703b4db493c6aec386d9b035ae198a.png)

切换密码字段