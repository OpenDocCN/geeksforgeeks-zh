# 如何创建带有可点击标签的 HTML 复选框？

> 原文：[https://www.geeksforgeeks.org/how-to-create-an-html-checkbox-with-a-clickable-label/](https://www.geeksforgeeks.org/how-to-create-an-html-checkbox-with-a-clickable-label/)

制作一个带有可点击标签的 HTML 复选框意味着当点击标签时，复选框打开/关闭。

**下面是方法：**

## 使用 `label` 标签内的复选框

```html
<!DOCTYPE html>
<html>
<head>
    <title>
        Create an HTML checkbox with a clickable label
    </title>
    <!-- Adding Style to label -->
    <style>
        .GFG {
            background-color: white;
            border: 2px solid black;
            color: green;
            padding: 5px 10px;
            text-align: center;
            display: inline-block;
            font-size: 20px;
            margin: 10px 10px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <h1>
        GeeksforGeeks
    </h1>
    <!-- Putting checkbox inside label tag -->
    <label class="GFG">
        <input type="checkbox"
               name="checkbox"
               value="Geeks">
        GFG
    </label>
</body>
</html>
```

**输出：**
**点击标签前：**
![](img/66db3f1fc785b5cb29a363ef8ddc828f.png)

**点击标签后：**
![](img/5b199df0956eb3d2de30bd03eab831b9.png)

## 使用 `for` 属性

使用 `input` 标签创建一个复选框，然后使用 `label` 标签的 `for` 属性为创建的复选框创建一个标签。

```html
<!DOCTYPE html>
<html>
<head>
    <title>
        Create an HTML checkbox
        with a clickable label
    </title>
    <!-- Adding Style to label -->
    <style>
        .GFG {
            background-color: white;
            border: 2px solid black;
            color: green;
            padding: 5px 10px;
            text-align: center;
            display: inline-block;
            font-size: 20px;
            margin: 10px 10px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <h1>GeeksforGeeks</h1>
    <!-- Using the for attribute in label -->
    <input type="checkbox"
           name="checkbox"
           id="checkID"
           value="Geeks">
    <label class="GFG"
           for="checkID">
        GFG
    </label>
</body>
</html>
```

**输出：**
**点击标签前：**
![](img/7be5eb59b43308d6aa5c4a3d1ce2af8b.png)

**点击标签后：**
![](img/c1fa622079c213dc5851a0dedbe1ff1d.png)