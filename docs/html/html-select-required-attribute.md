# HTML |选择所需属性

> 原文:[https://www . geesforgeks . org/html-select-required-attribute/](https://www.geeksforgeeks.org/html-select-required-attribute/)

**HTML <选择>所需属性**是一个布尔属性，用于*指定用户在提交表单*之前应该选择的值。

**语法:**

```html
<select required> 
```

**示例:**本示例说明了 select 元素中所需属性的使用。

```html
<!DOCTYPE html>
<html>

<head>
    <title>required Attribute</title>
    <style>
        h1,
        h2 {
            color: green;
            font-style: italic;
        }

        body {
            text-align: center;
        }
    </style>
</head>

<body>
    <h1>GeeksForGeeks</h1>
    <h2>HTML select required attribute</h2>
    <form action="">
        <select required>
            <option value="">None</option>
            <option value="ds">Data Structure</option>
            <option value="algo">Algorithm</option>
            <option value="os">Operating System</option>
            <option value="cn">Computer Network</option>
        </select>
        <input type="submit">
    </form>
</body>

</html>
```

**输出:**
![](img/3e0453543beb66854a36d83f63e17806.png)

**支持的浏览器:****HTML 选择所需属性**支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队