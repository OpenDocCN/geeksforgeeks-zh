# HTML | DOM 输入日期禁用属性

> 原文:[https://www . geesforgeks . org/html-DOM-input-date-disabled-property/](https://www.geeksforgeeks.org/html-dom-input-date-disabled-property/)

**输入日期禁用属性**用于设置或返回日期字段是否应禁用。如果元素被禁用，它将变得不可用和不可点击。浏览器通常以灰色呈现这些元素。
HTML 禁用属性由*日期禁用属性*反映。
**语法:**

*   **归还禁用属性:**

```html
inputdateObject.disabled
```

*   **设置禁用属性:**

```html
inputdateObject.disabled = true|false
```

**房产价值**

*   **true|false:** 用于指定日期字段是否应该禁用。默认为假。

**返回值:**返回一个布尔值，表示输入日期字段是否被禁用。

下面的程序说明了日期禁用属性:
**示例:**禁用日期字段。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>Input Date disabled Property in HTML
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
    <h2> Input Date disabled Property
  </h2>
    <br>

    <input type="date"
           id="test_Date">

<p>To disable the date field,
      double click the "Disable" button.
  </p>

    <button ondblclick="My_Date()">Disable
  </button>

    <script>
        function My_Date() {

            // Set disabled = true.
            document.getElementById(
              "test_Date").disabled = true;
        }
    </script>

</body>

</html>
```

**输出:**
**初始:**

![](img/fc28b5bcf02e0b191b2a9566d0ed9fdc.png)

**点击禁用按钮前:**

![](img/c11a921e62c8e91ba5f246d952570c29.png)

**点击禁用按钮后:**

![](img/c77b3ff158afe004ad2adbc82b8e7f5d.png)

**支持的浏览器:**

*   苹果 Safari
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   谷歌 Chrome
*   歌剧