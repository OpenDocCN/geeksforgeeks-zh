# HTML | 无大小属性

> 原文:[https://www . geesforgeks . org/html-frame-noresize-attribute/](https://www.geeksforgeeks.org/html-frame-noresize-attribute/)

**HTML <框架> noresize 属性**用于指定用户不能调整框架元素的大小。这种类型的属性用于查看框架元素的大小。

**语法:**

```html
<frame noresize="noresize">
```

**属性值:**

*   **noresize:** 定义用户不能调整大小的框架元素。

**注意:**HTML 5 不支持<框架>标签。

**示例:**

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title>HTML frame noresize Attribute</title> 
</head> 

<frameset cols="30%, 40%, 30%"> 
    <frame name="top"
        src="attr1.png" noresize="noresize"/> 
    <frame name="main"
        src="gradient3.png" marginwidth="30" /> 
    <frame name="bottom" marginwidth="30"
        src="col_last.png" marginwidth="40" /> 
</frameset> 

</html>                    
```

**输出:**
![](img/7b52ff25583e8d5ce93ad036fac877c9.png)

**支持的浏览器:**T2 HTML<框架>无大小属性支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧