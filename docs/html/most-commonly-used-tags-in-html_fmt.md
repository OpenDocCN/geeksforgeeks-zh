
# HTML 中最常用的标签

> 原文: [https://www.geeksforgeeks.org/most-commonly-used-tags-in-html/](https://www.geeksforgeeks.org/most-commonly-used-tags-in-html/)

HTML 包含许多预定义的标签。以下是一些描述：

## 文档结构标签

### html 标签

*   **语法:**

```html
<html> Statements... </html>
```

*   **代码:**

```html
<html>
    <head>
        <title>Title of your web page</title>
    </head>
    <body>HTML web page contents </body>
</html>
```

### Head 标签

*   **语法:**

```html
<head> Statements... </head>
```

*   **代码:**

```html
<head>Contains elements describing the document</head>
```

### 正文标签

*   **语法:**

```html
<body> Statements... </body>
```

*   **代码:**

```html
<body>The content of your HTML page</body>
```

### Title 标签

*   **语法:**

```html
<title> Statements... </title>
```

*   **代码:**

```html
<title>tab name</title>
```

## 内容容器标签

### 标题标签

*   **语法:**

```html
<h1> Statements... </h1>
<h2> Statements... </h2>
<h3> Statements... </h3>
<h4> Statements... </h4>
<h5> Statements... </h5>
<h6> Statements... </h6>
```

*   **代码:**

```html
<h1>Heading 1 </h1>
<h2>Heading 2 </h2>
<h3>Heading 3 </h3>
<h4>Heading 4 </h4>
<h5>Heading 5 </h5>
<h6>Heading 6 </h6>
```

### 段落标签

*   **语法:**

```html
<p> Statements... </p>
```

*   **代码:**

```html
<p>GeeksforGeeks: Computer science portal</p>
```

### 强调标记

*   **语法:**

```html
<em> Statements... </em>
```

*   **代码:**

```html
<em>GeeksforGeeks</em>
```

### 加粗标签

*   **语法:**

```html
<b> Statements... </b>
```

*   **代码:**

```html
<b>Bold word</b>
```

### 斜体标签

*   **语法:**

```html
<i> Statements... </i>
```

*   **代码:**

```html
<i>GeeksforGeeks</i>
```

### 小(文本)标签

*   **语法:**

```html
<small> Statements... </small>
```

*   **代码:**

```html
<small>Example</small>
```

### 下划线标记

*   **语法:**

```html
<u> Statements... </u>
```

*   **代码:**

```html
<u>GeeksforGeeks</u>
```

### 删除文本标签

*   **语法:**

```html
<strike> Statements... </strike>
```

*   **代码:**

```html
<strike>GeeksforGeeks</strike>
```

### 锚点标签

*   **语法:**

```html
<a href="..."> Statements... </a>
```

*   **代码:**

```html
<a href="https://www.geeksforgeeks.org/">
    GeeksforGeeks
</a>
```

### 列表标签

*   **语法:**

```html
<li> Statements... </li>
```

*   **代码:**

```html
<li>List item 1</li>
<li>List item 2</li>
```

### 有序列表标签

*   **语法:**

```html
<ol> Statements... </ol>
```

*   **代码:**

```html
<ol>
    <li>List item 1</li>
    <li>List item 2</li>
    <li>List item 3</li>
    <li>List item 4</li>
</ol>
```

### 无序列表标签

*   **语法:**

```html
<ul> Statements... </ul>
```

*   **代码:**

```html
<ul>
    <li>List item 1</li>
    <li>List item 2</li>
    <li>List item 3</li>
    <li>List item 4</li>
</ul>
```

### 注释标签

*   **语法:**

```html
<!-- Statements... -->
```

*   **代码:**

```html
<!--Comment section-->
```

### 滚动文本标签

*   **语法:**

```html
<marquee> Statements... </marquee>
```

*   **代码:**

```html
<marquee bgcolor="#cccccc" loop="-1"
scrollamount="2" width="100%">
    Example Marquee
</marquee>
```

### 中心标签

*   **语法:**

```html
<center> Statements... </center>
```

*   **代码:**

```html
<center>GeeksforGeeks</center>
```

### 字体标签

*   **语法:**

```html
<font> Statements ... </font>
```

*   **代码:**

```html
<font face="Times New Roman">Example</font>
```

## 空标签

### 断线标记

*   **语法:**

```html
<br>
```

*   **代码:**

```html
GeeksforGeeks<br>A computer science portal
```

### 图像标签

*   **语法:**

```html
<img>
```

*   **代码:**

```html
<img src="gfg.jpg" width="40" height="40" border="0">
```

### 链接标签

*   **语法:**

```html
<link>
```

*   **代码:**

```html
<head>
    <link rel="stylesheet" type="text/css" href="style.css">
</head>
```

### 横线规则标签

*   **语法:**

```html
<hr/>
```

*   **代码:**

```html
<hr width="50%" size="3" />
```

### 元标签

*   **语法:**

```html
<meta> Statements ... </meta>
```

*   **代码:**

```html
<meta name="Description" content="Description of your site">
<meta name="keywords" content="keywords describing your site">
```

## 表格标签

### 表标签

*   **语法:**

```html
<table> Statements... </table>
```

*   **代码:**

```html
<table border="4" cellpadding="2" cellspacing="2" width="100%">
    <tr>
        <td>Column 1</td>
        <td>Column 2</td>
    </tr>
</table>
```

### Tr 标签

*   **语法:**

```html
<tr> Statements... </tr>
```

*   **代码:**

```html
<table>
    <tr>
        <th>Month</th>
        <th>Savings</th>
    </tr>
    <tr>
        <td>January</td>
        <td>$100</td>
    </tr>
</table>
```

### Th 标签

*   **语法:**

```html
<th> Statements ... </th>
```

*   **代码:**

```html
<table>
    <tr>
        <th>Month</th>
        <th>Savings</th>
    </tr>
    <tr>
        <td>January</td>
        <td>$100</td>
    </tr>
</table>
```

### Td 标签

*   **语法:**

```html
<td> Statements ... </td>
```

*   **代码:**

```html
<table>
    <tr>
        <td>Cell A</td>
        <td>Cell B</td>
    </tr>
</table>
```

## 输入标签

### 表单标签

*   **语法:**

```html
<form> Statements ... </form>
```

*   **代码:**

```html
<form action="mailto:you@yourdomain.com">
    Name: <input name="Name" value="" size="80"><br>
    Email: <input name="Email" value="" size="80"><br>
    <br><center><input type="submit"></center>
</form>
```

### 提交输入标签

*   **语法:**

```html
<input>
```

*   **代码:**

```html
<form method=post action="/cgibin/example.cgi">
    <input type="text" style="color: #ffffff;
    font-family: Verdana; font-weight: bold;
    fontsize: 12px; background-color: #72a4d2;" size="10" maxlength="30">
    <input type="Submit" value="Submit">
</form>
```

### 下拉选项标签

*   **语法:**

```html
<option> Statements ... </option>
```

*   **代码:**

```html
<form method=post action="/cgibin/example.cgi">
    <center> Select an option:<select>
        <option>option 1</option>
        <option selected>option 2</option>
        <option>option 3</option>
    </select>
</form>
```

### 单选按钮标签

*   **语法:**

```html
<input>
```

*   **代码:**

```html
<form method=post action="/cgibin/example.cgi">
    Select an option:<br>
    <input type="radio" name="option"> Option 1
    <input type="radio" name="option" checked> Option 2
    <input type="radio" name="option"> Option 3
</form>
```

## 支持的浏览器

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队

HTML 是网页的基础，通过构建网站和网络应用程序用于网页开发。您可以通过以下 [HTML 教程](https://www.geeksforgeeks.org/html-tutorials/)和 [HTML 示例](https://www.geeksforgeeks.org/html-examples/)从头开始学习 HTML。
