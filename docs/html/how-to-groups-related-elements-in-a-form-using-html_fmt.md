# 如何使用 HTML 对表单中的相关元素进行分组？

> 原文：[https://www.geeksforgeeks.org/how-to-group-related-elements-in-a-form-using-html/](https://www.geeksforgeeks.org/how-to-group-related-elements-in-a-form-using-html/)

HTML5 中的 `<fieldset>` 标签用于在表单中创建一组相关的元素，并在元素上创建框。`<fieldset>` 标签在 HTML5 中是新的。

**语法：**

```html
<fieldset> Contents... </fieldset>
```

**属性：**

*   `disabled`：指定禁用相关表单元素组。
*   `form`：指定字段集所属的一个或多个表单。
*   `name`：指定字段集的名称。

**示例：**

## HTML

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        How to groups related elements
        in a form using HTML?
    </title>

    <style>
        h1,
        h2,
        .title {
            text-align: center;
        }

        fieldset {
            width: 50%;
            margin-left: 22%;
        }

        h1 {
            color: green;
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>

    <h2>
        How to groups related elements
        in a form using HTML?
    </h2>

    <form>
        <div class="titl">
            Suggest article for video:
        </div>

        <fieldset>
            <legend>JAVA:</legend>
            Title: <input type="text"><br>
            Link: <input type="text"><br>
            User ID: <input type="text">
        </fieldset>
        <br>
        <fieldset>
            <legend>PHP:</legend>
            Title: <input type="text"><br>
            Link: <input type="text"><br>
            User ID: <input type="text">
        </fieldset>
    </form>
</body>

</html>
```

**输出：**

![](img/7bb6e65747ee4ff77a906f4757013db5.png)

**支持的浏览器：**

*   Google Chrome
*   Microsoft Edge
*   Firefox
*   Safari
*   Opera