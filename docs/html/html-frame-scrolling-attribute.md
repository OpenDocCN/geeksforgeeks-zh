# HTML | 滚动属性

> 原文:[https://www . geesforgeks . org/html-frame-scrolling-attribute/](https://www.geeksforgeeks.org/html-frame-scrolling-attribute/)

**HTML <框架>滚动属性**用于指定滚动条是否会显示在<框架>元素中。基本上，当内容大于 Iframe 元素时，就使用滚动条。
**语法:**

```html
<frame scrolling="auto|yes|no">
```

**属性值:**

*   **自动:**有默认值。需要时会出现滚动条。
*   **是:**该值显示 iframe 元素中的滚动条。
*   **否:**该值不显示 iframe 元素中的滚动条。

**注意:**HTML 5 不支持<框架>标签。
**例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML frame scrolling Attribute
    </title>
</head>

<frameset cols="30%, 40%, 30%">

    <frame name = "left" src =
"https://media.geeksforgeeks.org/wp-content/uploads/20190328185307/gfg28.png"
            scrolling="auto" />

    <frame name="middle" src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190328185307/gfg28.png"
            scrolling="yes" />

    <frame name="right" src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190328185307/gfg28.png"
        scrolling="no" />

</frameset>

</html>  
```

**输出:**

![](img/4f137bc19eac7848e62bbd106b641f3c.png)

**支持的浏览器:**HTML<框架>滚动属性支持的浏览器如下:

*   internet Explorer(IE 9 之前)
*   火狐浏览器
*   Opera(最高 12.0)