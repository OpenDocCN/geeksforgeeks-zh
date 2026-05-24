# 内容属性如何与:CSS 中的选择器后一起使用？

> 原文:[https://www . geesforgeks . org/content-property-how-with-after-selector-in-CSS/](https://www.geeksforgeeks.org/how-content-property-is-used-with-after-selector-in-css/)

在本文中，我们将学习内容属性如何与 CSS 中的:after 选择器一起使用。after:选择器用于在任何选定的元素后插入一些内容。content 属性用于指定将要插入的内容。所以我们使用**:**选择器后的内容属性，在选中的元素后放一些东西。

**方法:**content 属性用于在任何选定元素之后或之前插入内容。所以我们使用**中的内容:在**选择器之后，在所选元素之后插入一些东西。

**语法:**

```html
element::after{
    content : value;
    css-properties...
}
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        p::after{
            content: "GeeksforGeeks";
            color: green;
            font-size: 30px;
            border-bottom: solid 5px green;
        }
    </style>
</head>

<body>
    <p style="font-size:30px;">
        Best website to learn coding: 
    </p>
</body>

</html>
```

**输出:**

![](img/ce63e9b14d2d587e7ee8f13266b4e1bd.png)