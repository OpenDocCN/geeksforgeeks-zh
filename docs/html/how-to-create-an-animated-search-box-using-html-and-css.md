# 如何使用 HTML 和 CSS 创建动画搜索框？

> 原文:[https://www . geesforgeks . org/如何使用 html 和 css 创建动画搜索框/](https://www.geeksforgeeks.org/how-to-create-an-animated-search-box-using-html-and-css/)

任务是使用 HTML 和 CSS 创建一个动画搜索框。搜索栏是网站最重要的组成部分之一。基本上是用来连接人和网站的。面对复杂的网络内容，用户通过搜索关键词来表达自己的需求，期望获得准确的信息和快速的结果。

**进场:**

**步骤 1:** 这里我们在 HTML 部分使用了一个输入元素。

```html
<input type="text" name="search" 
    placeholder="Search anything here .."> 
```

**第二步:**添加 CSS 代码，使其具有吸引力。

```html
input[type=text] {
    width: 150px;
    box-sizing: border-box;
    border: 4px solid green
    border-radius: 6px;
    font-size: 26px;
    background-color: white;
    background-image: url('searchicon.png');
    background-position: 10px 10px;  
    background-repeat: no-repeat;
    padding: 12px 20px 12px 40px;
    -webkit-transition: width 0.4s ease-in-out;
    transition: width 0.3s ease-in-out; 
}
input[type=text]:hover {
    width: 90%;
}
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        h1 {
            color: green;
        }

        input[type=text] {
            width: 150px;
            box-sizing: border-box;
            border: 4px solid green;
            border-radius: 6px;
            font-size: 26px;
            background-color: white;
            background-image: url('searchicon.png');
            background-position: 10px 10px;
            background-repeat: no-repeat;
            padding: 12px 20px 12px 40px;
            -webkit-transition: width 0.4s ease-in-out;
            transition: width 0.3s ease-in-out;
        }

        input[type=text]:hover {
            width: 90%;
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h2>
        Create an Animated Search 
        Box using HTML and CSS
    </h2>

    <form>
        <input type="text" name="search" 
            placeholder="Search..">
    </form>
</body>

</html>
```

**输出:**

![](img/fb3d4400b3085f050471e5d0ccc69b53.png)