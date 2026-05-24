# HTML | DOM 输入日期表单属性

> 原文:[https://www . geesforgeks . org/html-DOM-input-date-form-property/](https://www.geeksforgeeks.org/html-dom-input-date-form-property/)

**输入日期表单属性**用于*返回包含日期字段的表单的引用*。它是一个只读属性，在成功时返回一个表单对象，否则如果日期控件不在表单中，它将返回空值。
**语法:**

```html
inputdateObject.form
```

**返回值:**它返回一个字符串值，该值指定包含输入日期字段的表单的引用。

下面的程序说明了日期表单属性:
**示例:**返回包含<输入类型=“日期”>元素的表单的 id。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>Input Date form Property in HTML
  </title>
    <style>
        h1 {
            color: green;
        }

        h2 {
            font-family: Impact;
        }

        body {
            text-align: center;
        }
    </style>
</head>

<body>

    <h1>GeeksforGeeks</h1>
    <h2>Input Date form Property</h2>
    <br>

    <form id="Test_Form">
        Test date control:
        <input type="date"
               id="Test_Date">
    </form>

<p>To return the id of the form,
      double click the "Return
      Form Object" button.</p>

    <button ondblclick="My_Date()">
      Return Form Object
  </button>

    <p id="test"></p>

    <script>
        function My_Date() {

            // Returning form id.
            var d =
            document.getElementById("Test_Date").form.id;
            document.getElementById("test").innerHTML = d;
        }
    </script>

</body>

</html>
```

**输出:**
**点击按钮前:**

![](img/346e0d0c4efc3d91ec4d5c5361814838.png)

**点击按钮后:**

![](img/bb12a7ede05f15c06553fa0da6a88a8f.png)

**支持的浏览器:**

*   苹果 Safari
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   谷歌 Chrome
*   歌剧