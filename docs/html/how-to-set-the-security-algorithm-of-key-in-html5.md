# 如何在 HTML5 中设置密钥的安全算法？

> 原文:[https://www . geesforgeks . org/如何设置 html5 中的密钥安全算法/](https://www.geeksforgeeks.org/how-to-set-the-security-algorithm-of-key-in-html5/)

在本文中，我们将看到如何使用 HTML5 设置密钥的安全算法。设置密钥**的安全算法时，使用 T2 密钥根>标签**。此标记指定了用于表单的密钥对生成器字段。私钥保存在本地，公钥在发送表单时发送到服务器。该元素的目的是提供一种安全的用户身份验证方法。提交表单时，会生成两个密钥，一个私钥和一个公钥。公钥被发送到服务器，而私钥保存在本地。公钥用于构建客户端证书，该证书可用于在将来验证用户的身份。

**语法:**

```html
<keygen name = "name">
```

**示例:**

## HTML

```html
<!DOCTYPE html>
<html>

<body>
    <h1 style="color:green;">
        GeeksforGeeks
    </h1>

    <h2> 
        Specifying the security algorithm 
        of the key in HTML5
    </h2>

    <form>
        Username: <input type="text" name="name">
        <br><br> Encryption: <keygen name="key">
        <input type="submit">
    </form>
</body>

</html>
```