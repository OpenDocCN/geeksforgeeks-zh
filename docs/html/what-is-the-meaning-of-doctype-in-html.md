# DOCTYPE 在 HTML 中是什么意思？

> 原文:[https://www . geesforgeks . org/html 中 doctype 的含义是什么/](https://www.geeksforgeeks.org/what-is-the-meaning-of-doctype-in-html/)

*HTML 文档类型声明*或**文档类型**是网络浏览器用来获取网站是用什么版本的 HTML 编写的指令。它有助于浏览器理解如何解释文档，从而简化呈现过程。它既不是元素，也不是标签。文档类型应放在文档的*顶部*。它不能包含任何内容，也不需要结束标记。

**语法:**

```html
<!DOCTYPE html>
```

**例 1:**

## 超文本标记语言

```html
<!-- This resembles doctype for HTML5 file  -->
<!DOCTYPE html>
<html>

<head>
    <title>Page Title</title>
</head>

<body>
    <h2>Welcome To GFG</h2>
    <p>Default code has been loaded into the Editor.</p>
</body>

</html>
```

**例 2:**

## 超文本标记语言

```html
<!-- Below is declaration of XHTML 1.1 document -->
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.1//EN" 
    "http://www.w3.org/TR/xhtml11/DTD/xhtml11.dtd">
<html>

<head>
    <title>Page Title</title>
</head>

<body>
    <h2>Welcome To GFG</h2>
    <p>Default code has been loaded into the Editor.</p>
</body>

</html>
```

**以下是将包含在以下文档类型中的一些文档类型文件:**

*   XHTML 1.1

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.1//EN" 
"http://www.w3.org/TR/xhtml11/DTD/xhtml11.dtd">
```

*   XHTML 1.0 框架集

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Frameset//EN" 
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-frameset.dtd">
```

*   XHTML 1.0 过渡版

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" 
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
```

*   XHTML 1.0 严格

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" 
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
```

*   HTML 4.01 框架集

```html
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Frameset//EN" 
"http://www.w3.org/TR/html4/frameset.dtd">
```

*   HTML 4.01 过渡版

```html
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" 
"http://www.w3.org/TR/html4/loose.dtd">
```

*   HTML 4.01 严格

```html
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" 
"http://www.w3.org/TR/html4/strict.dtd">
```

*   HTML 5

```html
<!DOCTYPE html>
```