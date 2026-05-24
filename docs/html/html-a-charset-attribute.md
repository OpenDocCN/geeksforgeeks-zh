# HTML | a 字符集属性T3】

> 原文:[https://www.geeksforgeeks.org/html-a-charset-attribute/](https://www.geeksforgeeks.org/html-a-charset-attribute/)

**字符集属性**用于*指定链接文档的字符集，即引用 href 属性*的文档。

**语法:**

```html
<a charset="value">
```

**属性值:**它包含指定外部脚本字符编码的值字符集。

*   **“ISO-8859-1”:**用于拉丁字母的标准编码。
*   **“UTF-8”:**用于 Unicode 的字符编码。兼容 ASCII。

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
      HTML a charset Attribute
  </title>
</head>

<body>
    <p>Welcome to
        <a charset="UTF-8"
           href="https://ide.geeksforgeeks.org/"> 
                GeeksforGeeks 
            </a>
    </p>
</body>

</html>
```

**输出:**
![](img/c696cdd5bd0eb525a24029dc1cbc88b7.png)

**支持的浏览器:**没有浏览器支持 *HTML < a >字符集属性*。