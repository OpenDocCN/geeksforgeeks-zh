# 使用 HTML 和 CSS 设计一个跑车动画

> 原文:[https://www . geesforgeks . org/design-a-running-car-animation-use-html-and-CSS/](https://www.geeksforgeeks.org/design-a-running-car-animation-using-html-and-css/)

**项目介绍:**在这个项目中，我们要用 HTML 和带有音效的 CSS 实现一辆在赛道上行驶的汽车。这个项目的前提是 **HTML、CSS、**和 **JavaScript。**

**文件结构:**

*   【index.html】
*   风格。半铸钢ˌ钢性铸铁(Cast Semi-Steel)
*   剧本。射流研究…

**HTML 代码:**在下面的代码中，我们将*天空* div 放置成覆盖整个网页。之后，树、轨道、汽车被放在天空上，最后，车轮被安装在汽车上，这样它们就可以旋转，我们可以为行驶的汽车创建一个动画。我们已经使用文件 *style.css* 添加了样式，并应用了来自 *script.js* **的声音效果。**

## HTML

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content=
      "width=device-width, initial-scale=1.0">
    <title>Lamborghini car animation</title>
    <link rel="stylesheet" href="style.css">
    <script src="script.js"></script>
</head>
<body>
    <div class="sky">
        <div class="tree"></div>
        <div class="track"></div>
        <div class="car"></div>
        <div class=" wheel wheel1"></div>
        <div class="wheel wheel2"></div>
    </div>
</body>
</html>
```