# HTML | DOM Textarea 必需属性

> 原文: [https://www.geeksforgeeks.org/html-dom-textarea-required-property/](https://www.geeksforgeeks.org/html-dom-textarea-required-property/)

**DOM Textarea 必需属性**用于*设置*或*返回*提交表单前是否必须填写输入元素。此属性用于反映 `required` 属性。

## 语法

*   用于返回 `required` 属性:

```html
textareaObject.required
```

*   用于设置 `required` 属性:

```html
textareaObject.required = true|false
```

## 属性值

*   `true`: 指定提交表单前必须填写 `textarea` 字段。
*   `false`: 有默认值。它指定 `textarea` 字段不是表单的必需部分。

## 返回值

返回一个布尔值，表示在提交表单之前必须填写 `textarea` 字段。

## 示例-1

在说明如何**返回 `required` 属性**的 HTML 程序中。

### 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>DOM required textarea Property</title>
    <style>
        h1,
        h2 {
            color: green;
            font-style: italic;
        }

        body {
            text-align: center;
        }
    </style>
</head>

<body>
    <h1>GeeksForGeeks</h1>
    <h2>DOM required textarea Property</h2>

    <form action="/action_page.php">
        <textarea id="GFG"
                  rows="7"
                  cols="50"
                  name="comment"
                  required>
        </textarea>

        <input type="submit">
    </form>
    <br>
    <br>

    <button onclick="myGeeks()">
      Try it
    </button>

    <p id="sudo"></p>

    <script>
        function myGeeks() {
            // Return Textarea property
            var x = document.getElementById("GFG").required;

            document.getElementById("sudo").innerHTML = x;
        }
    </script>
</body>

</html>
```

**输出:**
**点击试用按钮前:**

![](img/c8e71a39d7a984ac2849589c04dab39d.png)

**点击试用按钮后:**

![](img/9122c4fd70dbada7de6c0f1365c3b67f.png)

## 示例-2

在说明如何**设置 `required` 属性**的 HTML 程序中。

### 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>DOM required textarea Property</title>
    <style>
        h1,
        h2 {
            color: green;
            font-style: italic;
        }

        body {
            text-align: center;
        }
    </style>
</head>

<body>
    <h1>GeeksForGeeks</h1>
    <h2>DOM required textarea Property</h2>

    <form action="/action_page.php">
        <textarea id="GFG"
                  rows="7"
                  cols="50"
                  name="comment">
        </textarea>

        <input type="submit">
    </form>
    <br>
    <br>
    <button onclick="myGeeks()">
      Try it
    </button>

    <p id="sudo"></p>

    <script>
        function myGeeks() {
            // Set Textarea property.
            var x = document.getElementById("GFG").required = true;

            document.getElementById("sudo").innerHTML = "Now the value of required attribute is set to True";
        }
    </script>
</body>

</html>
```

**输出:**
**点击按钮前:**

![](img/c8e71a39d7a984ac2849589c04dab39d.png)

**点击按钮后:**

![](img/2e24a250bb14f453cf8b08ed2c834bfc.png)

## 支持的浏览器

支持的 `required textarea` 属性如下:

*   Google Chrome
*   Microsoft Edge
*   Firefox
*   Opera
*   Safari