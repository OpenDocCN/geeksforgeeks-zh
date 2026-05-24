# CSS `empty-cells` 属性

> 原文: [https://www.geeksforgeeks.org/css-empty-cells-property/](https://www.geeksforgeeks.org/css-empty-cells-property/)

此属性用于指定是否在表格的空单元格中显示边框。

**语法:**
```html
empty-cells: show|hide|initial|inherit;
```

**默认值:**
* `show`

**属性值:**

**`show` 属性:** 该属性用于显示空单元格的边框。
* **语法:**
```html
empty-cell: show;
```
* **示例:**
### Hypertext Markup Language
```html
<!DOCTYPE html>
<html>
    <head>
        <title>empty-cell property</title>
        <style>
            table.geek {
                empty-cells: show;
            }
            td {
                text-align:center;
            }
            .gfg {
                font-size:40px;
                font-weight:bold;
                color:green;
            }
            .geeks {
                font-size:17px;
            }
        </style>
    </head>
    <body>
        <center>
            <div class = "gfg">GeeksforGeeks</div>
            <div class = "geeks">A computer science portal for geeks</div>
            <h2>empty-cells: show;</h2>
            <table class="geek" border="1">
                <tr>
                    <td>C Programming</td>
                    <td>C++ Programming</td>
                </trA>
                <tr>
                    <td>Java</td>
                    <td></td>
                </tr>
            </table>
        </center>
    </body>
</html>
```
* **输出:**
![image](img/04c9650fa1d8ca13fb021cb7931522e8.png)

**`hide` 属性:** 该属性用于隐藏表格中空单元格的边框。
* **语法:**
```html
empty-cell: hide;
```
* **示例:**
### Hypertext Markup Language
```html
<!DOCTYPE html>
<html>
    <head>
        <title>empty-cell property</title>
        <style>
            table.geek {
                empty-cells: hide;
            }
            td {
                text-align:center;
            }
            .gfg {
                font-size:40px;
                font-weight:bold;
                color:green;
            }
            .geeks {
                font-size:17px;
            }
        </style>
    </head>
    <body>
        <center>
            <div class = "gfg">GeeksforGeeks</div>
            <div class = "geeks">A computer science portal for geeks</div>
            <h2>empty-cells: show;</h2>
            <table class="geek" border="1">
                <tr>
                    <td>C Programming</td>
                    <td>C++ Programming</td>
                </trA>
                <tr>
                    <td>Java</td>
                    <td></td>
                </tr>
            </table>
        </center>
    </body>
</html>
```
* **输出:**
![image](img/0cd0aaad122ebe54ee824ba386b2b326.png)

**`initial` 属性:** 该属性用于设置默认属性。
* **语法:**
```html
empty-cell: initial;
```
* **示例:**
### Hypertext Markup Language
```html
<!DOCTYPE html>
<html>
    <head>
        <title>empty-cell property</title>
        <style>
            table.geek {
                empty-cells: initial;
            }
            td {
                text-align:center;
            }
            .gfg {
                font-size:40px;
                font-weight:bold;
                color:green;
            }
            .geeks {
                font-size:17px;
            }
        </style>
    </head>
    <body>
        <center>
            <div class = "gfg">GeeksforGeeks</div>
            <div class = "geeks">A computer science portal for geeks</div>
            <h2>empty-cells: show;</h2>
            <table class="geek" border="1">
                <tr>
                    <td>C Programming</td>
                    <td>C++ Programming</td>
                </trA>
                <tr>
                    <td>Java</td>
                    <td></td>
                </tr>
            </table>
        </center>
    </body>
</html>
```
* **输出:**
![image](img/04c9650fa1d8ca13fb021cb7931522e8.png)

**`inherit` 属性:** 此属性用于从其父级继承属性。
* **语法:**
```html
empty-cell: inherit;
```
* **示例:**
### Hypertext Markup Language
```html
<!DOCTYPE html>
<html>
    <head>
        <title>empty-cell property</title>
        <style>
            table.geek {
                empty-cells: initial;
            }
            .g4g {
                empty-cells: inherit;
            }
            td {
                text-align:center;
            }
            .gfg {
                font-size:40px;
                font-weight:bold;
                color:green;
            }
            .geeks {
                font-size:17px;
            }
        </style>
    </head>
    <body>
        <center>
            <div class = "gfg">GeeksforGeeks</div>
            <div class = "geeks">A computer science portal for geeks</div>
            <h2>empty-cells: show;</h2>
            <table class="geek" border="1">
                <tr>
                    <td>C Programming</td>
                    <td>Algorithm</td>
                </tr>
                <tr>
                    <td></td>
                    <td>
                        <table class="g4g" border="1">
                            <tr>
                                <td>DP</td>
                                <td>Backtracking</td>
                            </tr>
                            <tr>
                                <td>Sorting</td>
                                <td></td>
                            </tr>
                        </table>
                    </td>
                </tr>
            </table>
        </center>
    </body>
</html>
```
* **输出:**
![image inherit property](img/7bed8c3e4562ceafde7784987e754e78.png)

**支持的浏览器:** CSS `empty-cells` 属性支持的浏览器如下:
* 谷歌 Chrome 1.0
* internet explorer 8.0
* Firefox 1.0
* Opera 4.0
* Safari 1.2