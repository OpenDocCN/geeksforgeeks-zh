# 如何使用 HTML 在表单中添加单选按钮？

> 原文：[https://www.geeksforgeeks.org/how-to-add-radio-buttons-in-form-using-html/](https://www.geeksforgeeks.org/how-to-add-radio-buttons-in-form-using-html/)

我们知道单选按钮仅用于从几个选项中选择一个选项。一般以 HTML 形式使用。

`方法:` 要在网页中添加单选按钮，HTML 提供了一个`<input>`元素，`type`属性设置为`"radio"`。

`语法:`

```html
<input type="radio">  
```

`示例:` 下面的代码说明了如何在网页中添加单选按钮。

## HTML

```html
<!DOCTYPE html>
<html>

<head>

<style>
        body {
            text-align: center;
        }
        h2 {
            color: green;
        }
    </style>
</head>

<body>
    <h2>
        GeeksforGeeks
    </h2>

    <h3>
        How to add a Radio Buttons in form using HTML?
    </h3>
    <h4>
        Select Gender
    </h4>

    Male
    <input type="radio" checked=true name="user_gender">
    Female
    <input type="radio" name="user_gender">

</body>

</html>
```

`输出:`

![](img/9d037399c7c54a57846b26ad3a1596d9.png)