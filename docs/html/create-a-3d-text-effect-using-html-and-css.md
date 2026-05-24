# 使用 HTML 和 CSS 创建 3D 文本效果

> 原文:[https://www . geesforgeks . org/create-a-3d-text-effect-using-html-and-CSS/](https://www.geeksforgeeks.org/create-a-3d-text-effect-using-html-and-css/)

3D 文本效果是网页设计领域中最常用的文本效果之一。作为设计师或前端开发人员，应该知道如何创建 3D 文本效果。今天，我们将探讨一种最简单易行的方法来创建 3D 文本。
**进场:**3D 文字动画效果由[文字-阴影](https://www.geeksforgeeks.org/css-shadow-effect/)属性设计。应用多个文本阴影的原因是为了给人一种 3D 的感觉，就好像我们只应用一个(或单一的)文本阴影一样，它对单词中的所有字母都是一样的。但是对于 3D 效果，我们希望每个字母和每个角度(基本上是 X 和 Y 坐标以及模糊半径)有不同的阴影厚度。现在让我们看看上述方法的实现。
**HTML 代码:**在本节中，我们使用了一个< h1 >标签，上面有我们想要应用 3D 效果的单词。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0" />
    <title>3D Text Effect</title>
</head>

<body>
    <h1>GeeksforGeeks</h1>
</body>

</html>
```

**CSS 代码:**T2]

*   **第一步:**我们做的第一件事就是将< h1 >元素对中，提供身体背景。
*   **步骤 2:** 现在，对 h1 元素应用过渡。持续时间可以根据您的需要进行调整。
*   **步骤 3:** 现在在 h1 元素上应用文本阴影。应用多个文本阴影的概念已经在文章开头的方法中解释过了。

**提示:**我们必须选择应用一个仅在鼠标悬停时可见的效果，但是如果您希望该效果始终可见，请移除悬停选择器。

## 半铸钢ˌ钢性铸铁(Cast Semi-Steel)

```html
<style>
    body {
        background: green;
    }

    h1 {
        margin: 300px auto;
        text-align: center;
        color: white;
        font-size: 8em;
        transition: 0.5s;
        font-family: Arial, Helvetica, sans-serif;
    }

    h1:hover {
        text-shadow: 0 1px 0 #ccc, 0 2px 0 #ccc,
                     0 3px 0 #ccc, 0 4px 0 #ccc,
                     0 5px 0 #ccc, 0 6px 0 #ccc,
                     0 7px 0 #ccc, 0 8px 0 #ccc,
                     0 9px 0 #ccc, 0 10px 0 #ccc,
                     0 11px 0 #ccc, 0 12px 0 #ccc,
                     0 20px 30px rgba(0, 0, 0, 0.5);
    }
</style>
```

**完整代码:** Tn 在这一部分，我们将结合以上两个部分来创建鼠标悬停时的 3D 文本动画效果。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>3D Text Effect</title>

    <style>
        body {
            background: green;
        }

        h1 {
            margin: 300px auto;
            text-align: center;
            color: white;
            font-size: 8em;
            transition: 0.5s;
            font-family: Arial, Helvetica, sans-serif;
        }

        h1:hover {
            text-shadow: 0 1px 0 #ccc, 0 2px 0 #ccc,
                0 3px 0 #ccc, 0 4px 0 #ccc,
                0 5px 0 #ccc, 0 6px 0 #ccc,
                0 7px 0 #ccc, 0 8px 0 #ccc,
                0 9px 0 #ccc, 0 10px 0 #ccc,
                0 11px 0 #ccc, 0 12px 0 #ccc,
                0 20px 30px rgba(0, 0, 0, 0.5);
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>
</body>

</html>
```

**输出:**

![](img/ea0b902617181fb5dba6fcf7171873fd.png)