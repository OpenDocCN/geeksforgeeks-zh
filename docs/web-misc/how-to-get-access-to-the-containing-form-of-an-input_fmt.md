# 如何获取输入元素的包含表单？

> 原文：[https://www.geeksforgeeks.org/how-to-get-access-to-the-containing-form-of-an-input/](https://www.geeksforgeeks.org/how-to-get-access-to-the-containing-form-of-an-input/)

本文的目标是从给定的`<input>`元素中选择并访问其所属的`<form>`元素。这里将讨论一些重要的技术，我们将使用 JavaScript。

## 方法

1.  首先选择`<input>`元素。
2.  使用`.form`属性或`.closest('form')`方法来访问其父`<form>`元素。

## 示例 1：使用 `.form` 属性

该示例使用上述方法中的`.form`属性。

```html
<!DOCTYPE HTML>
<html>

<head>
    <title>
        Get access to the containing form of an input.
    </title>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.1/jquery.min.js">
    </script>
</head>

<body id="body" align="center">
    <h1 style="color:green;">
        GeeksforGeeks
    </h1>
    <p id="GFG_UP" style="font-size: 15px; font-weight: bold;">
    </p>
    <form id="formElement">
        Input_1:
        <input id="input1" type="text" />
        <br>
        <input type="checkbox" name="input_2">
        Input_2
    </form>
    <br>
    <button onclick="GFG_Fun()">
        click here
    </button>
    <p id="GFG_DOWN" style="font-size: 24px; font-weight: bold; color:green;">
    </p>
    <script>
        var el_up = document.getElementById('GFG_UP');
        var el_down = document.getElementById('GFG_DOWN');
        var input = document.getElementById('input1');
        el_up.innerHTML = "Click on the button to select the " +
            "form element from the input element.";

        function GFG_Fun() {
            var form = input.form;
            el_down.innerHTML =
                "Id of <form> is '" + $(form).attr("id") + "'";
        }
    </script>
</body>

</html>
```

### 输出

*   点击按钮前：
    [![](img/79b626b88aadca6872ca89d5740e02b9.png)](https://media.geeksforgeeks.org/wp-content/uploads/20190904131750/Screenshot-from-2019-09-04-13-15-44.png)
*   点击按钮后：
    [![](img/25b8efa233f54561a2d38f0376693cbb.png)](https://media.geeksforgeeks.org/wp-content/uploads/20190904131752/Screenshot-from-2019-09-04-13-15-46.png)

## 示例 2：使用 `.closest()` 方法

该示例使用上述方法中的`.closest()`方法。

```html
<!DOCTYPE HTML>
<html>

<head>
    <title>
        Get access to the containing form of an input.
    </title>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.1/jquery.min.js">
    </script>
</head>

<body id="body" align="center">
    <h1 style="color:green;">
        GeeksforGeeks
    </h1>
    <p id="GFG_UP" style="font-size: 15px; font-weight: bold;">
    </p>
    <form id="formElement">
        Input_1:
        <input id="input1" type="text" />
        <br>
        <input type="checkbox" name="input_2">
        Input_2
    </form>
    <br>
    <button onclick="GFG_Fun()">
        click here
    </button>
    <p id="GFG_DOWN" style="font-size: 24px; font-weight: bold; color:green;">
    </p>
    <script>
        var el_up = document.getElementById('GFG_UP');
        var el_down = document.getElementById('GFG_DOWN');
        var input = document.getElementById('input1');
        el_up.innerHTML = "Click on the button to select the " +
            "form element from the input element.";

        function GFG_Fun() {
            var form = $(input).closest('form');
            el_down.innerHTML =
                "Id of <form> is '" + $(form).attr("id") + "'";
        }
    </script>
</body>

</html>
```

### 输出

*   点击按钮前：
    [![](img/79b626b88aadca6872ca89d5740e02b9.png)](https://media.geeksforgeeks.org/wp-content/uploads/20190904131750/Screenshot-from-2019-09-04-13-15-44.png)
*   点击按钮后：
    [![](img/25b8efa233f54561a2d38f0376693cbb.png)](https://media.geeksforgeeks.org/wp-content/uploads/20190904131752/Screenshot-from-2019-09-04-13-15-46.png)