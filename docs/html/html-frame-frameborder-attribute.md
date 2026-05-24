# HTML | 边框属性

> 原文:[https://www . geesforgeks . org/html-frame-frame border-attribute/](https://www.geeksforgeeks.org/html-frame-frameborder-attribute/)

**HTML <框架>框架边框属性**用于指定框架之间是否应该显示边框。为此，我们使用两个值 0 和 1，其中 0 定义无边框，1 定义边框。

**语法**

```html
<frame frameborder="1|0"> 
```

**属性值:**

*   **0:** 有默认值。它确定了一个州的边界。
*   **1:** 设置边框关闭状态。

**示例:**

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title>
        HTML frame frameborder Attribute
    </title> 
</head> 

<frameset cols="30%, 40%, 30%"> 

    <frame name="left" src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190401113144/gfg_200X2001.png"
            frameborder="1" /> 

    <frame name="main" src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190328185307/gfg28.png"
             frameborder="1" /> 

    <frame name="bottom" src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190807114330/GFG115.png"
             frameborder="0" /> 

</frameset> 

</html>
```

**输出:**
![](img/d008d68d701efe9d405330c8d179ef78.png)

**支持的浏览器:**HTML<框架>框架边框属性支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧