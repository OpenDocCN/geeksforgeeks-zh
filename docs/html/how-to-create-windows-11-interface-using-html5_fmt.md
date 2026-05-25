# 如何用 HTML5 创建 Windows 11 界面？

> 原文：[https://www.geeksforgeeks.org/how-to-create-windows-11-interface-using-html5/](https://www.geeksforgeeks.org/how-to-create-windows-11-interface-using-html5/)

在本文中，我们将看到如何使用 HTML5 创建 Windows 11 界面。

**方法：** 为了创建 Windows 11 界面，我们将使用 `HTML`、`CSS` 和 `JavaScript`。如果你想改变设计，你可以增加更多的功能。在本文中，我们将整个事情分为三个不同的部分：**创建结构**、**设置结构**和**添加功能**。

下面是上述方法的逐步实现。

## 第 1 步：创建基本结构

在这一节中，我们将使用 HTML 为 Windows 11 界面创建基本结构。我们会将**标题**设为**“Try Windows 11”**并使用 [`<img>`](https://www.geeksforgeeks.org/html-img-src-attribute/) 标签添加必要的图片。还使用 [`<link>`](https://www.geeksforgeeks.org/html-link-tag/) 标签添加必要的链接。

**HTML 代码：** 该代码用于添加图片和链接来构建网站。它没有任何 CSS 属性。我们将使用 `<div>` 标签创建各种 div，并给它们指定各自的类名。

```html
<!DOCTYPE html>
<html>

<head>
    <title>Try Windows 11</title>

    <link rel="shortcut icon"
        href="https://media.geeksforgeeks.org/wp-content/uploads/20210914203818/faviconWindows.png"
        type="image/x-icon">

    <!-- Linking the CSS stylesheet -->
    <link rel="stylesheet" href="styles.css">
</head>

<body>
    <div class="taskbar">
        <img src="https://media.geeksforgeeks.org/wp-content/uploads/20210914203932/icons-300x37.PNG" alt="">
        <img class="right" src="https://media.geeksforgeeks.org/wp-content/uploads/20210914204052/taskbar-200x37.PNG"
            alt="">
    </div>

    <div class="startmenu">
        <img src="https://media.geeksforgeeks.org/wp-content/uploads/20210914204232/startmenu-289x300.PNG" alt="">
    </div>

    <div class="wallpaper">
        <img src="https://media.geeksforgeeks.org/wp-content/uploads/20210914204725/windows11-300x169.jpg" alt="">
    </div>

    <!-- Linking the external JavaScript -->
    <script src="script.js"></script>
</body>

</html>
```

## 第 2 步：设计结构样式

在前面的部分中，我们已经创建了 Windows 11 界面的结构。现在我们将在上面添加一些 CSS 属性。不同的类会有不同的属性。

名为 `.taskbar` 的类将具有 CSS 属性，例如：

1.  `background-color: #F3F3F3;`（设置元素的背景色）。
2.  `width: 100%;`（设置元素的宽度）。
3.  `position: absolute;`（设置元素的位置并指定元素使用的定位方法）。
4.  `bottom: 0;`（影响定位元素的垂直位置）。
5.  `display: flex;`（指定元素的显示行为（渲染框的类型））。
6.  `z-index: 110;`（指定元素的堆叠顺序）。
7.  `justify-content: center;`（当项目没有水平使用主轴上的所有可用空间时，对齐柔性容器的项目）。

名为 `.right` 的类将具有 CSS 属性，例如：

1.  `justify-self: flex-end;`（设置框在其对齐容器内沿相应轴对齐的方式）。
2.  `position: absolute;`（设置元素的位置，指定元素使用的定位方法）。
3.  `right: 0;`（影响给定元素的水平位置）。
4.  `margin: 6px 0;`（在元素周围创建间距）。
5.  `height: 85%;`（设置元素的高度）。

名为 `.startmenu` 的类将具有 CSS 属性，例如：

1.  `position: absolute;`（指定元素使用的定位方法类型）。
2.  `bottom: -655px;`（影响定位元素的垂直位置）。
3.  `width: 100%;`（设置元素的宽度）。
4.  `text-align: center;`（指定元素中文本的水平对齐方式）。
5.  `transition: all 0.3s ease-in;`（允许在给定的持续时间内平滑地更改属性值）。

```css
body{
    overflow: hidden;
    height: 100vh;
}
.taskbar{
    background-color: #F3F3F3;
    width: 100%;
    position: absolute;
    bottom: 0;
    display: flex;
    z-index: 110;
    justify-content: center;
}
.right{
    justify-self: flex-end;
    position: absolute;
    right: 0;
    margin: 6px 0;
    height: 85%;
}
.startmenu{
    position: absolute;
    bottom: -655px;
    width: 100%;
    text-align: center;
    transition: all 0.3s ease-in;
}
.startmenu img{
    border-radius: 8px;
}
.wallpaper img{
    height: 900px;
}
```

## 第 3 步：给网站增加功能

我们将为开始菜单和任务栏编写 JavaScript。首先我们将创建两个名为 `taskbar` 和 `startmenu` 的变量，然后在这个变量中我们将使用 [`document.getElementsByClassName()`](https://www.geeksforgeeks.org/html-dom-getelementsbyclassname-method/) 方法，该方法返回文档中具有指定类名的所有元素的集合，作为一个 `HTMLCollection` 对象。

现在在任务栏中，我们将添加一个 [`addEventListener`](https://www.geeksforgeeks.org/javascript-addeventlistener-with-examples/) 为一个 `click` 事件，将一个事件处理程序附加到文档中。在它里面，我们将创建一个 `if-else` 语句：如果 `startmenu` 的 `bottom` 属性是 `50px`，那么将其更新为 `-655px`；否则，如果不是 `50px`，那么将其更新为 `50px`。这将使任务栏响应。

```javascript
let taskbar = document.getElementsByClassName("taskbar")[0]
let startmenu = document.getElementsByClassName("startmenu")[0]

taskbar.addEventListener("click", ()=>{
    console.log("clicked");
    if(startmenu.style.bottom == "50px"){
        startmenu.style.bottom = "-655px"
    }
    else{
        startmenu.style.bottom = "50px"
    }
})
```

**输出：**

<video class="wp-video-shortcode" id="video-680605-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210915113442/output-final.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210915113442/output-final.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210915113442/output-final.mp4)</video>