# HTML | 边缘属性

> 原文:[https://www . geesforgeks . org/html-frame-margin width-attribute/](https://www.geeksforgeeks.org/html-frame-marginwidth-attribute/)

**HTML <框架>边距宽度属性**用于指定框架元素中内容的左右边距。

**语法:**

```html
<frame marginwidth="pixels">
```

**属性值:**

**pixels:**

**pixels**

**注意:**HTML 5 不支持该属性。使用 CSS 属性代替该属性。

下面的例子说明了 HTML 中的边距属性:

**示例:**

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title>
        HTML frame marginWidth Attribute
    </title> 
</head> 

<frameset cols="30%, 40%, 30%"> 

    <frame name = "left" src =
"https://media.geeksforgeeks.org/wp-content/uploads/20190401113144/gfg_200X2001.png"/> 

    <frame name="middle" src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190328185307/gfg28.png"
            marginwidth="30" /> 

    <frame name="right" src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190807114330/GFG115.png"
        marginwidth="40" /> 

</frameset> 

</html>
```

**输出:**
![](img/ade25616d9698769949825dc0b9a823d.png)

**支持的浏览器:**HTML<框架>边框属性支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧