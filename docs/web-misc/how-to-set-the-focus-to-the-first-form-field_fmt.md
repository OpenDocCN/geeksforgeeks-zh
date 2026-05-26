# 如何将焦点设置到第一个表单域？

> 原文：[https://www.geeksforgeeks.org/how-to-set-the-focus-to-the-first-form-field/](https://www.geeksforgeeks.org/how-to-set-the-focus-to-the-first-form-field/)

在本文中，我们将讨论如何将焦点放在第一个表单域上。通过将焦点设置在第一个表单域上，我们指示用户从哪里开始。它增加了网页中表单的可读性。有多种方法可以做到这一点，我们将用合适的例子解释其中的两种。

*   使用 HTML [`autofocus`](https://www.geeksforgeeks.org/html-input-autofocus-attribute/) 属性
*   在 JavaScript 中使用 [`focus()`](https://www.geeksforgeeks.org/javascript-focus/) 方法

## 方法 1：使用 HTML `autofocus` 属性

`autofocus` 是一个布尔属性，与表单中的 `<input>` 元素一起使用。当页面加载时，表单域会自动聚焦。

### 示例

```html
<!DOCTYPE html>
<html>

<head>
    <title>Set focus to the first form field</title>
</head>

<body>
    <h1>
        <center>Welcome to GFG</center>
    </h1>
    <center>
        <form>
            Email id: <input type="text" id="input1" autofocus />
            <br /><br />

            Password: <input type="text" id="input2" />
            <br /><br />

            <button type="submit">Submit</button>
        </form>
    </center>
</body>

</html>
```