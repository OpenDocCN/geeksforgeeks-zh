# 如何使用 CSS 创建自定义横幅背景？

> 原文:[https://www . geesforgeks . org/how-create-custom-banner-background-use-CSS/](https://www.geeksforgeeks.org/how-to-create-custom-banner-background-using-css/)

在现代网页设计中，自定义背景已经成为横幅背景的一种流行设计。自定义背景有无数种设计。这个设计纯粹是基于一个人的想象力和创造力。自定义背景的一些常见示例包括波浪背景、倾斜背景等。

本文将展示用于创建锯片背景的方法，因为它的底部类似于锯子。它也被称为之字形图案。

**做法:**做法是先在底部创建一串小三角形，然后沿着 X 轴旋转，使其形成叶片状外观。

**HTML 代码:**在 HTML 部分，创建了< div >元素，该元素将用于保存模式。

## 超文本标记语言

```html
<html lang="en">
<head>
  <title>
    Custom background
  </title>
</head>
<body>
  <div class="geeks">
  </div>
</body>
</html>
```

**CSS 代码:**可以使用以下步骤定义 CSS:

*   **第一步:**给身体提供一个基本的背景色。
*   **第 2 步:**使用不同的背景颜色将创建的 div 与中心对齐。
*   **步骤 3:** 使用 before 选择器，使用**线性渐变**属性创建一个小的三角形链，具有相同的度数，但保持其中一个为负。
*   **第 4 步:**使用 rotate()函数旋转 X 轴上的三角形。

## 半铸钢ˌ钢性铸铁(Cast Semi-Steel)

```html
<style>
    body {
        background: green;
    }

    .geeks {
        position: absolute;
        top: 50%;
        width: 100%;
        height: 50%;
        background: white;
    }

    .geeks::before {
        content: "";
        position: absolute;
        width: 100%;
        height: 15px;
        display: block;
        background: linear-gradient(
            -45deg, transparent, 33.33%,
            green 33.33%, green 66.66%, 
            transparent 66.66%),
            linear-gradient(45deg, transparent, 
            33.33%,green 33.33%, green 66.66%, 
            transparent 66.66%);
        background-size: 30px 60px;
        transform: rotateX(180deg);
    }
</style>
```

**完整代码:**在本节中，我们将结合以上两个部分，使用 HTML 和 CSS 制作自定义横幅背景。

## 超文本标记语言

```html
<html lang="en">

<head>
    <title>
        Custom background
    </title>
    <style>
        body {
            background: green;
        }

        .geeks {
            position: absolute;
            top: 50%;
            width: 100%;
            height: 50%;
            background: white;
        }

        .geeks::before {
            content: "";
            position: absolute;
            width: 100%;
            height: 15px;
            display: block;
            background: linear-gradient(
                -45deg, transparent, 33.33%,
                green 33.33%, green 66.66%, 
                transparent 66.66%),
                linear-gradient(45deg, transparent,
                33.33%,green 33.33%, green 66.66%,
                transparent 66.66%);
            background-size: 30px 60px;
            transform: rotateX(180deg);
        }
    </style>
</head>

<body>
    <div class="geeks">
    </div>
</body>

</html>
```

**输出:**

![](img/af90a5602a1d4fb879748b9550073508.png)