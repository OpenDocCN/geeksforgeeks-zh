# HTML |选择名称属性

> 原文:[https://www.geeksforgeeks.org/html-select-name-attribute/](https://www.geeksforgeeks.org/html-select-name-attribute/)

**HTML <选择>名称属性**用于*为下拉列表*指定名称。它用于在提交表单后引用表单数据，或者引用 JavaScript 中的元素。

**语法:**

```html
<select name="text"> 
```

**属性值:**包含指定<选择>元素名称的值，即名称。

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML Select name Attribute
    </title>
</head>

<body style="text-align:center;">

    <h1 style="color:green;"> 
        GeeksforGeeks 
    </h1>

    <h2 style="font-family: Impact;"> 
       HTML Select name Attribute 
    </h2>
    <br> Select your preferred 
  course from the drop-down list:
    <br>

    <select name="Courses Titles" id="myCourses">
        <option value="C++">c++</option>
        <option value="Placement">Placement</option>
        <option value="Java">Java</option>
        <option value="Python">Python</option>
    </select>

</body>

</html>
```

**输出:**
![](img/b0289c39f7d3aaddad5d7fe99b13ac25.png)

**支持的浏览器:**

*   谷歌 Chrome
*   火狐浏览器
*   边缘
*   歌剧
*   苹果 Safari