# 如何用 php/html 显示无效输入的错误？

> 原文:[https://www . geesforgeks . org/如何用 php-html 显示无效输入错误/](https://www.geeksforgeeks.org/how-to-display-an-error-for-invalid-input-with-php-html/)

[PHP 可以很容易地嵌入到 HTML 文件中，HTML 代码也可以写在一个 PHP 文件中。](https://www.geeksforgeeks.org/php/)PHP 与像 HTML 这样的客户端语言的区别在于，PHP 代码是在服务器上执行的，而 HTML 代码是直接在浏览器上呈现的。用 HTML 和 PHP 显示无效输入的错误。

**进场:**

出现以下情况时，在无效错误上显示错误

*   输入文本框留空。
*   输入错误。

**PHP 代码:**以下是“form.php”的代码，在后面的 HTML 代码中用到。

要在 PHP 中显示无效输入，请设置 HTML 中输入文本框的名称。首先检查所有字段的空字段，然后验证其正确性。如果所有字段都正确，则显示成功消息。如果用户给出的输入是错误的，那么它将显示一条消息“无效输入！!"。

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```html
<?php
$nameError = "";
$emailError = "";
$passwordError = "";
$mobileError = "";
$success = "";

function validate_input($input) {
    $input = trim($input);
    $input = stripslashes($input);
    $input = htmlspecialchars($input);
    return $input;
}

if(isset($_POST['form_submit'])) {
    $name = $_POST['name'];
    $password = $_POST['password'];
    $email = $_POST['user_email'];
    $mobile = $_POST['mobile'];

    if (empty($_POST["name"])) {
        $nameError = "Name is required";
    } else {
        $name = validate_input($_POST["name"]);

        if($name == 'chetan') {
            $success= "Thank you ". $name.", ";
            echo $success;
        }
    }

    if (empty($_POST["email"])) {
        $emailError = "Email is required";
    } else {
        $email = validate_input($_POST["email"]);

        if($email == 'test@email.com') {
            $success= $email." is correct";
            echo $success;
        }
    }

    if (empty($_POST["password"])) {
        $passwordError = "Password is required";
    } else {
        $password = validate_input($_POST["password"]);

        if($password == 'test@123') {
            $success= $password." is correct";
            echo $success;
        }
    }

    if (empty($_POST["mobile"])) {
        $mobileError = "Mobile is required";
    } else {
        $mobile = validate_input($_POST["mobile"]);

        if($mobile == '123456789') {
            $success= $mobile." is correct";
            echo $success;
        }
    }
    if(empty($success))
        echo "Invalid input!!!";
}
?>
```

**HTML 代码:**下面的代码使用了上面的 PHP“form . PHP”代码。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">

<head>
    <meta charset="utf-8">
    <title>Form</title>
</head>

<body>
    <form action="form.php" method="POST">
        <input type="text" name="name" 
            placeholder="Enter name">

        <input type="password" name="password"
            placeholder="Password">

        <input type="email" name="user_email" 
            placeholder="yourname@gamil.com">

        <input type="tel" name="mobile" 
            placeholder="Mobile no">

        <button type="submit" name="form_submit">
            Submit
        </button>
    </form>
</body>

</html>
```

**输出:**

*   用户输入不正确

    ```html
    Invalid input!!!
    ```

*   用户正确输入

    ```html
    Thank you chetan, 123456789 is correct
    ```