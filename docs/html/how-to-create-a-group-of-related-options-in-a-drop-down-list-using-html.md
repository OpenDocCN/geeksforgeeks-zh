# 如何用 HTML 在下拉列表中创建一组相关选项？

> 原文:[https://www . geesforgeks . org/如何使用 html 创建一组相关选项下拉列表/](https://www.geeksforgeeks.org/how-to-create-a-group-of-related-options-in-a-drop-down-list-using-html/)

我们可以使用 **[<选项组>标签](https://www.geeksforgeeks.org/html-optgroup-tag/)** 标签在下拉列表中定义一组相关选项，用于在下拉列表中创建一组相同类别的选项。当项目列表很长时，标签是必需的。

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        How to define a group of
        related options in a
        drop-down list?
    </title>

    <style>
        body {
            text-align: center;
        }

        .gfg {
            font-size: 40px;
            font-weight: bold;
            color: green;
        }

        .geeks {
            font-size: 17px;
        }
    </style>
</head>

<body>
    <div class="gfg">GeeksforGeeks</div>
    <div class="geeks">
        A computer science portal for geeks
    </div>
    <h2>
        How to define a group of related
        options in a drop-down list
    </h2>
    <select>
        <optgroup label="Programming Languages">
            <option value="C">C</option>
            <option value="C++">C++</option>
            <option value="Java">Java
        </optgroup>
        <optgroup label="Scripting Language">
            <option value="JavaScript">JavaScript</option>
            <option value="PHP">PHP</option>
            <option value="Shell">Shell</option>
        </optgroup>
    </select>
</body>

</html>
```

**输出:**
![](img/17069c39cf5ab7f89d4e4b63fd3e8c81.png)

**支持的浏览器如下:**

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队