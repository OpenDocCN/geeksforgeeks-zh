# HTML、XML 和 DHTML 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-html-xml-and-dhtml/](https://www.geeksforgeeks.org/difference-between-html-xml-and-dhtml/)

## 1. HTML

*   `HTML` 代表超文本标记语言。
*   用于设计文档布局和指定超链接。
*   高速浏览器如何显示文本、图片和其他支持的媒体。
*   支持多媒体和新的页面布局功能。
*   易于与其他编程语言集成。
*   `HTML` 由一系列元素组成。
*   提供了许多标签来控制网页上信息的呈现，例如 `<h1>`、`<li>`、`<hr>` 等。

**HTML 语法:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Page Title</title>
</head>
<body>

<h1>Hello World</h1>
<p>This is GeeksForGeeks portal.</p>

</body>
</html>
```

## 2. XML

*   `XML` 代表可扩展标记语言。
*   标记语言是一种识别文档结构的机制。
*   `XML` 设计用于存储和传输数据。
*   `XML` 设计用于描述自身。
*   `XML` 定义了向文档添加标签的标准方式。
*   提供了定义标签及其结构关系的能力。
*   `XML` 文档的所有语义要么由处理它们的应用程序定义，要么由样式表定义。

**XML 语法:**

```html
<note>
  <to>Geeks</to>
  <from>GeeksForGeeks</from>
  <heading>Welcome to new course</heading>
  <body>Don't forget to signup before this weekend!</body>
</note>
```

## 3. DHTML

*   `DHTML` 代表动态 `HTML`。
*   `DHTML` 是一个术语，用于描述使网页动态和交互的技术。
*   `DHTML` 指的是每次查看时都会改变的网页内容。例如，图形可以根据用户操作（如鼠标点击）从一个位置移动到另一个位置。
*   使网页能够响应用户输入，而无需向 Web 服务器发送请求。
*   描述了 `HTML`、样式表和脚本的组合，允许对文档进行动画处理。

**DHTML 语法:**

```html
<html>
<head>
<script type="text/javascript">
function sameInfo()
{
for (i=0; i<document.myForm1.option.length; i++)
    {
    document.myForm2.option[i].value=document.myForm1.option[i].value;
    }
}
</script>
</head>
<body>

<form name="myForm1">
First name: <input type="text" name="option"><br />
Last name: <input type="text" name="option"><br />
Address: <input type="text" name="option"><br />
E-mail: <input type="text" name="option"><br />
<br />
<input type="button" onclick="sameInfo()" value="Same information below"><br />
</form>

<form name="myForm2">
First name: <input type="text" name="option"><br />
Last name: <input type="text" name="option"><br />
Address: <input type="text" name="option"><br />
E-mail: <input type="text" name="option"><br />
</form>

</body>
</html>
```