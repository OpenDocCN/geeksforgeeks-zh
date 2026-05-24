# HTML | DOM 样式 tableLayout 属性

> 原文:[https://www . geesforgeks . org/html-DOM-style-table layout-property/](https://www.geeksforgeeks.org/html-dom-style-tablelayout-property/)

DOM Style **tableLayout** 属性用于**设置**或**返回**表格及其单元格、行和列的布局方式。

**语法:**

*   它返回表格布局属性

    ```html
    object.style.tableLayout
    ```

*   用于设置表格布局属性

    ```html
    object.style.tableLayout = "auto | fixed | initial | inherit"
    ```

**返回值:**它返回一个字符串值，该值代表用于表格的表格布局算法。

**属性值:**

*   **固定:**该值用于根据表格宽度设置列宽，与内容无关。
*   **auto:** 此值用于根据单元格中最宽的不可破解内容设置表格和列的宽度。这是默认值。
*   **初始值:**用于将该属性设置为默认值。
*   **继承:**这将从其父级继承属性。

**示例-1:** 使用固定值。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Style tableLayout property
    </title>
    <style>
        table,
        td {
            border: 1px solid;
        }

        #table1 {
            width: 100%;
        }
    </style>
</head>

<body>
    <h1 style="color: green">
      GeeksforGeeks
  </h1>
    <b>
      DOM Style tableLayout
  </b>

    <table id="table1">
        <tr>
            <td>GeeksforGeeks is a 
              computer science portal.</td>
            <td>DOM Style tableLayout</td>
        </tr>
        <tr>
            <td>Article 1</td>
            <td>Article 2</td>
        </tr>
        <tr>
            <td>Article 3</td>
            <td>Article 4</td>
        </tr>
    </table>

    <button onclick="changetableLayout()">
      Change tableLayout
  </button>

    <script>
        function changetableLayout() {
            document.querySelector(
              "#table1").style.tableLayout = 
              "fixed";
        }
    </script>

</body>

</html>
```

**输出:**

*   点击按钮前:
    ![fixed-before](img/25a3eda70527a0c7b341416e8e78d2e7.png)
*   点击按钮后:
    ![fixed-after](img/f7065dfa53e0f237c1a9a37152d664a5.png)

**示例-2:** 使用自动值。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Style tableLayout property
    </title>
    <style>
        table,
        td {
            border: 1px solid;
        }

        #table1 {
            width: 100%;
            table-layout: fixed;
        }
    </style>
</head>

<body>
    <h1 style="color: green">
      GeeksforGeeks
  </h1>
    <b>
      DOM Style tableLayout
  </b>

    <table id="table1">
        <tr>
            <td>GeeksforGeeks is a 
              computer science portal.</td>
            <td>DOM Style tableLayout</td>
        </tr>
        <tr>
            <td>Article 1</td>
            <td>Article 2</td>
        </tr>
        <tr>
            <td>Article 3</td>
            <td>Article 4</td>
        </tr>
    </table>

    <button onclick="changetableLayout()">
      Change tableLayout
  </button>

    <script>
        function changetableLayout() {
            document.querySelector(
              "#table1").style.tableLayout =
              "auto";
        }
    </script>

</body>

</html>
```

**输出:**

*   点击按钮前:
    ![auto-before](img/7dfc942a0d643a3aa058028e92ee7d92.png)
*   点击按钮后:
    ![auto-after](img/f237469dbfc70cf6af2f2f5cf732a79b.png)

**示例-3:** 使用初始值。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Style tableLayout property
    </title>
    <style>
        table,
        td {
            border: 1px solid;
        }

        #table1 {
            width: 100%;
            table-layout: fixed;
        }
    </style>
</head>

<body>
    <h1 style="color: green">
      GeeksforGeeks
  </h1>
    <b>DOM Style tableLayout</b>

    <table id="table1">
        <tr>
            <td>GeeksforGeeks is a 
              computer science portal.</td>
            <td>DOM Style tableLayout</td>
        </tr>
        <tr>
            <td>Article 1</td>
            <td>Article 2</td>
        </tr>
        <tr>
            <td>Article 3</td>
            <td>Article 4</td>
        </tr>
    </table>

    <button onclick="changetableLayout()">
      Change tableLayout
  </button>

    <script>
        function changetableLayout() {
            document.querySelector(
              "#table1").style.tableLayout =
              "initial";
        }
    </script>

</body>

</html>
```

**输出:**

*   点击按钮前:
    ![initial-before](img/1bf00e70b0551a1e376ab8da5cd8de2d.png)
*   点击按钮后:
    ![initial-after](img/34af732cef62de46636af38ed54753dd.png)

**示例-4:** 使用继承值。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Style tableLayout property
    </title>
    <style>
        #parent {
            table-layout: fixed;
        }

        table,
        td {
            border: 1px solid;
        }

        #table1 {
            width: 100%;
        }
    </style>
</head>

<body>
    <h1 style="color: green">
      GeeksforGeeks
  </h1>
    <b>DOM Style tableLayout</b>

    <div id="parent">
        <table id="table1">
            <tr>
                <td>GeeksforGeeks is a
                  computer science portal.</td>
                <td>DOM Style tableLayout</td>
            </tr>
            <tr>
                <td>Article 1</td>
                <td>Article 2</td>
            </tr>
            <tr>
                <td>Article 3</td>
                <td>Article 4</td>
            </tr>
        </table>
    </div>

    <button onclick="changetableLayout()">
      Change tableLayout
  </button>

    <script>
        function changetableLayout() {
            document.querySelector(
              "#table1").style.tableLayout =
              "inherit";
        }
    </script>

</body>

</html>
```

**输出:**

*   点击按钮前:
    ![inherit-before](img/9b52062b951ec3874b6048b58aed8966.png)
*   点击按钮后:
    ![inherit-after](img/0229d4b8706ffd0599a54c54c5bdea00.png)

**支持的浏览器:***tableLayout*属性支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   苹果 Safari