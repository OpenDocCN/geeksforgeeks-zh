# HTML | <input>名称属性

> 原文:[https://www.geeksforgeeks.org/html-input-name-attribute/](https://www.geeksforgeeks.org/html-input-name-attribute/)

**HTML <输入>名称属性**用于*为<输入>元素*指定名称。它用于在提交表单后引用表单数据，或者引用 JavaScript 中的元素。

**语法:**

```html
<input name="name"> 
```

**属性值:**它包含一个描述<输入>元素名称的单一值名称。

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML Input name Attribute
    </title>
</head>

<body style="text-align:center;">

    <h1>GeeksForGeeks</h1>

    <h2>HTML Input name Attribute</h2>
    <form id="myGeeks">
        <input type="text"
               id="text_id" 
               name="geeks"
               pattern="[A-Za-z]{3}" 
               value="Manas Chhabra">
    </form>
    <br>
</body>

</html>
```

**输出:**
![](img/cefa8ef52c05eee4aff05119a9873b75.png)

**支持的浏览器:**

*   谷歌 Chrome 1.0
*   Firefox 1.0
*   Edge 2.0
*   Opera 1.0
*   苹果 Safari 1.0