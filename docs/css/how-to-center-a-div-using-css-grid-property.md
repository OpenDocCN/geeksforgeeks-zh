# 如何使用 CSS 网格属性将居中？

> 原文: [https://www .极客们。组织/如何使用 css-grid-property/](https://www.geeksforgeeks.org/how-to-center-a-div-using-css-grid-property/) 对中心进行划分

在本文中，我们将学习使用 CSS 的 [grid](https://www.geeksforgeeks.org/css-grid-property/) 属性将一个 HTML[**<div>**](https://www.geeksforgeeks.org/div-tag-html/)**元素居中。**

 **使用网格水平居中 **< div >** 元素。使用设置为网格的显示属性，即*显示:网格*；然后使用属性 [*放置-物品:居中；*](https://www.geeksforgeeks.org/css-place-items-property/)

**示例:**以下示例演示了使用*网格*属性将< div >设置为中心。

## HTML

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" 
          content="width=device-width, initial-scale=1.0">
    <style>
        .grid{
            display: grid;
            place-items:  center;
            color: green;
            font-size: 25px;
            height : 500px;
        }
    </style>
</head>
<body>
    <div class="grid">
      <p>Geeks for Geeks</p>
    </div>
</body>
</html>
```

**输出:**

![](img/9fa9771e3868ca8fa3bb6fffd8479f89.png)

中心 div 使用高度

**示例 2:** 我们将演示一个示例，其中我们没有为设置高度 **< div >** 。结果将在中心但仅在 x 轴方向，而通过设置*高度*我们可以在两个轴上居中 **< div >** 。

## HTML

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" 
          content="width=device-width, initial-scale=1.0">

    <style>
        .grid{
            display: grid;
            place-items:  center;
            color: green;
            font-size: 25px;
        }
    </style>
</head>
<body>
    <div class="grid">
      <p>Geeks for Geeks</p>
    </div>
</body>
</html>
```

**输出:**

![](img/6ebcee52e0498fc6fee760ebd8ef3853.png)

中心在 x 轴上**