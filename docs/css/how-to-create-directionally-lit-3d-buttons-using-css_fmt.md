# 如何使用 CSS 创建定向点亮的 3D 按钮？

> 原文：[https://www.geeksforgeeks.org/how-to-create-directionally-lit-3d-buttons-using-css/](https://www.geeksforgeeks.org/how-to-create-directionally-lit-3d-buttons-using-css/)

定向照明三维按钮是一种按钮显示为三维图形的效果。这些按钮是使用 `HTML` 和 `CSS` 创建的。

方法：制作 `HTML` 对象动画的最佳方法是使用 `CSS` 变换，并在不同阶段设置变换。

*   创建一个 `HTML` 文件。
*   链接提供所有动画效果的 `CSS` 文件到我们的 `HTML`。
*   添加三个 `<a>` 标签来创建按钮并为它们分配特定的类。

`HTML` 代码：

## HTML

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" 
        content="IE=edge">
    <meta name="viewport" content
        ="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" 
        href="buttons.css" type="text/css">
    <link rel="stylesheet" href=
"https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
</head>

<body>
    <div>
        <ul>
            <li id="like">
                <a href="#">
                    <i class="fa fa-thumbs-up"></i>
                    Like
                </a>
            </li>
            <li id="comment">
                <a href="#">
                    <i class="fa fa-comment"></i>
                    Comment
                </a>
            </li>
            <li id="share">
                <a href="#">
                    <i class="fa fa-share"></i>
                    Share
                </a>
            </li>
        </ul>
    </div>
</body>

</html>
```