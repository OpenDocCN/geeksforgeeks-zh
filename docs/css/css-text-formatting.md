# CSS |文本格式

> 原文:[https://www.geeksforgeeks.org/css-text-formatting/](https://www.geeksforgeeks.org/css-text-formatting/)

CSS 文本格式属性用于设置文本格式和文本样式。
CSS 文本格式包括以下属性:
1。文-色
2。文本对齐
3。正文-装饰
4。文本转换
5。文本缩进
6。字母间距
7。行高
8。文字方向
9。文影
10。字距
**1。文本颜色**
文本颜色属性用于设置文本的颜色。
**文本颜色可以通过使用名称“红色”、十六进制值“#ff0000”或其 RGB 值“rgb(255，0，0)”来设置。**

```html
Syntax:
body
{
color:color name;
}
```

示例:

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
<style>
h1
{
color:red;
}
h2
{
color:green;
}
</style>
</head>
<body>
<h1>
GEEKS FOR GEEKS
</h1>
<h2>
TEXT FORMATTING
</h2>
</body>
</html>
```

```html
OUTPUT:
```

**2。文本对齐**
文本对齐属性用于设置文本的水平对齐。
**文本可以设置为左、右、居中和对齐。**
在对齐方式中，线条被拉伸，使左右边距变直。

```html
Syntax:
body
{
text-align:alignment type;
}
```

示例:

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
<style>
h1
{
color:red;
text-align:center;
}
h2
{
color:green;
text-align:left;
}
</style>
</head>
<body>
<h1>
GEEKS FOR GEEKS
</h1>
<h2>
TEXT FORMATTING
</h2>
</body>
</html>
```

```html
OUTPUT:
```

**3。文本装饰**
文本装饰用于在文本中添加或移除装饰。
**文字装饰可以是下划线、跨线、穿线或无。**

```html
Syntax:
body
{
text-decoration:decoration type;
}
```

示例:

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
<style>
h1
{
color:red;
text-decoration:underline;
}
</style>
</head>
<body>
<h1>
GEEKS FOR GEEKS
</h1>
<h2>
TEXT FORMATTING
</h2>
</body>
</html>
```

```html
OUTPUT:
```

**4。文本转换**
文本转换属性用于更改文本的大小写，大写或小写。
**文本转换可以是大写、小写或大写。**
大写用于将每个单词的首字母改为大写。

```html
Syntax:
body
{
text-transform:type;
}
```

示例:

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
<style>
h2
{
text-transform:lowercase;
}
</style>
</head>
<body>
<h1>
GEEKS FOR GEEKS
</h1>
<h2>
TEXT FORMATTING
</h2>
</body>
</html>
```

```html
OUTPUT:
```

**5。文本缩进**
文本缩进属性用于缩进段落的第一行。
尺寸可以用 px、cm、pt 表示。

```html
Syntax:
body
{
text-indent:size;
}
```

示例:

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
<style>
h2
{
text-indent:80px;
}
</style>
</head>
<body>
<h1>
GEEKS FOR GEEKS
</h1>
<h2>
This is text formatting properties.<br>
Text indentation property is used to indent the first line of the paragraph.
</h2>
</body>
</html>
```

```html
OUTPUT:
```

**6。字母间距**
该属性用于指定文本字符之间的间距。
尺寸可以用 px 给出。

```html
Syntax:
body
{
letter-spacing:size;
}
```

示例:

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
<style>
h2
{
letter-spacing:4px;
}
</style>
</head>
<body>
<h1>
GEEKS FOR GEEKS
</h1>
<h2>
This is text formatting properties.
</h2>
</body>
</html>
```

```html
OUTPUT:
```

**7。线条高度**
该属性用于设置线条之间的间距。

```html
Syntax:
body
{
line-height:size;
}
```

示例:

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
<style>
h2
{
line-height:40px;
}
</style>
</head>
<body>
<h1>
GEEKS FOR GEEKS
</h1>
<h2>
This is text formatting properties.<br>
This property is used to set the space between the lines.
</h2>
</body>
</html>
```

```html
OUTPUT:
```

**8。文本方向**
文本方向属性用于设置文本的方向。
**使用 rtl 可以设置方向:从右向左。**
从左到右是文本的默认方向。

```html
Syntax:
body
{
direction:rtl;
}
```

示例:

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
<style>
h2
{
direction: rtl;
text-align:center;
}
</style>
</head>
<body>
<h1>
GEEKS FOR GEEKS
</h1>
<h2><bdo dir="rtl">
This is text formatting properties.
</bdo>
</h2>
</body>
</html>
```

```html
OUTPUT:
```

**9。文本阴影**
文本阴影属性用于给文本添加阴影。
可以指定文字的水平大小、垂直大小和阴影颜色。

```html
Syntax:
body
{
text-shadow:horizontal size vertical size color name;
}
```

示例:

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
<style>
h1
{
text-shadow:3px 1px blue;
}
</style>
</head>
<body>
<h1>
GEEKS FOR GEEKS
</h1>
<h2>
This is text formatting properties.
</h2>
</body>
</html>
```

```html
OUTPUT:
```

**10。**字间距
字间距用于指定行的字之间的间距。
尺寸可以用 px 给出。

```html
Syntax:
body
{
word-spacing:size;
}
```

示例:

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
<style>
h2
{
word-spacing:15px;
}
</style>
</head>
<body>
<h1>
GEEKS FOR GEEKS
</h1>
<h2>
This is text formatting properties.
</h2>
</body>
</html>
```

```html
OUTPUT:
```

**支持的浏览器:**

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队

CSS 是网页的基础，通过设计网站和网络应用程序用于网页开发。你可以通过以下 [CSS 教程](https://www.geeksforgeeks.org/css-tutorials/)和 [CSS 示例](https://www.geeksforgeeks.org/css-examples/)从头开始学习 CSS。