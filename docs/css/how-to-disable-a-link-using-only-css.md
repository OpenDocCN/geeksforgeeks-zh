# 如何仅使用 CSS 禁用链接？

> 原文:[https://www . geesforgeks . org/如何禁用仅使用 css 的链接/](https://www.geeksforgeeks.org/how-to-disable-a-link-using-only-css/)

要使用 CSS 禁用链接，可以使用 **[指针事件](https://www.geeksforgeeks.org/css-pointer-events-property/)** 属性，该属性设置页面中的元素在单击元素时是否必须响应。 **[指针事件](https://www.geeksforgeeks.org/css-pointer-events-property/)** 属性用于指定元素是否显示为指针事件以及是否显示在指针上。

下面的例子说明了这种方法:

**示例 1:** 下面的代码显示了属性事件的使用，其中“a”标记被禁用，没有光标(禁用的光标指针在“a”标记上)

```html
<!DOCTYPE html>
<html>

<head>
    <title>Disable Link using CSS</title>
    <style type="text/css">
        .not-active {
            pointer-events: none;
            cursor: default;
        }
    </style>
</head>

<body>
    <center>
        <h1 style="color: green;">GeeksforGeeks</h1>
        <h3>A Computer Science Portal for Geeks</h3>
        <b>Disabled link:</b> To visit us 
          <a href="www.geeksforgeeks.org"
             class="not-active">Click Here</a>
        <br>
        <br>
        <b>Enabled link:</b> To use our ide 
          <a href=
             "https://ide.geeksforgeeks.org/tryit.php">
            Click Here</a>
    </center>
</body>

</html>
```

**输出:**我们可以注意到，虽然它看起来像一个链接，但当我们将指针放在它上面或点击它时，什么都没有发生。
T3】

**示例 2:** 该代码显示了应用于“a”标签的 CSS，这样看起来链接被禁用，为此，可以使用**颜色**和**文本装饰**属性。

```html
<!DOCTYPE html>
<html>

<head>
    <title>Disable Link using CSS</title>
    <style type="text/css">
        .not-active {
            pointer-events: none;
            cursor: default;
            text-decoration: none;
            color: black;
        }
    </style>
</head>

<body>
    <center>
        <h1 style="color: green;">GeeksforGeeks</h1>
        <h3>A Computer Science Portal for Geeks</h3>
        <b>Disabled link:</b> To visit us
        <a href="www.geeksforgeeks.org" class="not-active">
          Click Here
        </a>
        <br>
        <br>
        <b>Enabled link:</b> To use our ide
        <a href="https://ide.geeksforgeeks.org/tryit.php">
            Click Here
        </a>
    </center>
</body>

</html>
```

**输出:**这里可以看到，它甚至看起来不像链接。
T3】