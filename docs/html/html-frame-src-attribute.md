# HTML | src 属性

> 原文:[https://www.geeksforgeeks.org/html-frame-src-attribute/](https://www.geeksforgeeks.org/html-frame-src-attribute/)

**HTML <框架> src 属性**用于*指定在框架*中显示的文档网址。

**语法:**

```html
<frame src="URL">
```

**属性值:**包含单个值 **URL** ，指定文档的来源。该网址的可能值为:

*   **绝对 URL:** 指向另一个网站。
*   **相对 URL:** 它指向网站内的一个文件。

**注意:**HTML 5 不支持<框架> src 属性。

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>HTML frame src Attribute</title>
</head>

<frameset cols="30%, 40%, 30%">
    <frame name="top"
           src="attr1.png" />
    <frame name="main" 
           src="gradient3.png" />
    <frame name="bottom" 
           src="col_last.png" />
</frameset>

</html>
```

**输出:**
![](img/ba6fb598c4722f3b93ee843c511d185d.png)

**支持的浏览器:**支持的浏览器 **HTML <框架> src 属性**如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧