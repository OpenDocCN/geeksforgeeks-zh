# 如何使用 CSS 创建雕版文字效果？

> 原文:[https://www . geesforgeks . org/如何使用-css/](https://www.geeksforgeeks.org/how-to-create-carved-text-effect-using-css/) 创建雕刻文本-效果

雕刻的文本效果也称为浮雕效果，因为它看起来像是文本被浮雕在背景上。它在 CSS 中也被称为神经变形。当我们想要给我们的网站一个干净清爽的外观时，就会使用这种效果。嵌入的文本可以与背景颜色相同，也可以是不同的颜色。我们将看到相同的颜色类型。
**方法:**该方法是首先通过给文本赋予与背景相同的颜色来使其不可见，然后给文本赋予一个薄的阴影，以便它由于边框阴影而变得可见。
**HTML 代码:**在本节中，我们创建了两个 div 和一个包装在嵌套 div 中的文本。您也可以使用 h1 代替嵌套的 div 标记。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width,
                   initial-scale=1.0">
    <title>Embedded Text</title>
    <link href=
"https://fonts.googleapis.com/css2?family=Baloo+Chettan+2:wght@700&display=swap"
          rel="stylesheet">
</head>
<body>
   <div class="geeks">
       <div class="gfg">
           GeeksforGeeks
       </div>
   </div>
</body>
</html>
```

**CSS 代码:**在 CSS 中，首先我们做了一些基本的样式，比如将文本对齐到中心并为其提供背景，以及设置 google-font。然后，正如在方法中所讨论的，我们已经给了我们的文本与背景相同的颜色。现在我们已经使用了黑色和白色薄阴影的组合来给我们的文本周围一种轮廓效果，这使得我们的文本现在可见。
**提示:**阴影和文字可以使用任何颜色，但一定要尽可能保持阴影稀疏。

## 半铸钢ˌ钢性铸铁(Cast Semi-Steel)

```html
<style>
    body {
        font-family: 'Baloo Chettan 2', cursive;
        background: green;
    }

    .geeks {
        position: absolute;
        top: 50%;
        left: 40%;

    }

    .gfg {
        position: relative;
        display: block;
        font-size: 80px;
        color: green;
        text-shadow: -1px 1px 1px
            rgba(0, 0, 0, .4), 1px -1px 0
            rgba(255, 255, 255, 1);
    }
</style>
```