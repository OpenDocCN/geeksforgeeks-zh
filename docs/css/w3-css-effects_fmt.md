# W3.CSS 效果

> 原文: [https://www.geeksforgeeks.org/w3-css-effects/](https://www.geeksforgeeks.org/w3-css-effects/)

W3.CSS 为 web 开发人员提供了各种效果。它们可以大致分为三类。它们是:
*   不透明度
*   灰度
*   乌贼（深褐色）

## 不透明度效果

有四个不透明度效果类:

| Sr 号 | 类名 | 描述 |
| --- | --- | --- |
| 1. | `w3-opacity-min` | 目标元素的不透明度设置为 **0.75**。 |
| 2. | `w3-opacity` | 目标元素的不透明度设置为 **0.6**。 |
| 3. | `w3-opacity-max` | 目标元素的不透明度设置为 **0.25**。 |
| 4. | `w3-hover-opacity` | 悬停时目标元素的不透明度设置为 **0.6**。 |

**示例:**

```html
<!DOCTYPE html>
<html>
<head>
    <!-- Adding W3.CSS file through external link -->
    <link rel="stylesheet" href="https://www.w3schools.com/w3css/4/w3.css">
</head>
<body>
    <!-- w3-container is used to add 16px padding to any HTML element. -->
    <!-- w3-center is used to set the content of the element to the center. -->
    <div class="w3-container w3-center">
        <!-- w3-text-green sets the text colour to green. -->
        <!-- w3-xxlarge sets font size to 32px. -->
        <h2 class="w3-text-green w3-xxlarge">Welcome To GFG</h2>
    </div>

    <!-- Images with Opacity Effects -->
    <div class="w3-row w3-row-padding w3-center">
        <!-- Minimum Opacity -->
        <div class="w3-col m3 l3">
            <img class="w3-image w3-opacity-min" src="gfg.png">
            <p>
                <span class="w3-text-red">Class</span><br>
                <span class="w3-text-blue">w3-opacity-min</span>
            </p>
        </div>
        <!-- Normal Opacity -->
        <div class="w3-col m3 l3">
            <img class="w3-image w3-opacity" src="gfg.png">
            <p>
                <span class="w3-text-red">Class</span><br>
                <span class="w3-text-blue">w3-opacity</span>
            </p>
        </div>
        <!-- Maximum Opacity -->
        <div class="w3-col m3 l3">
            <img class="w3-image w3-opacity-max" src="gfg.png">
            <p>
                <span class="w3-text-red">Class</span><br>
                <span class="w3-text-blue">w3-opacity-max</span>
            </p>
        </div>
        <!-- On Hover Opacity -->
        <div class="w3-col m3 l3">
            <img class="w3-image w3-hover-opacity" src="gfg.png">
            <p>
                <span class="w3-text-red">Class</span><br>
                <span class="w3-text-blue">w3-hover-opacity</span>
            </p>
        </div>
    </div>
</body>
</html>
```

**输出:**

![](img/0e3442dbe1aeb69f1db589cce1b92395.png)

## 灰度效果

共有 4 个灰度效果类:

| Sr 编号 | 类名称 | 说明 |
| --- | --- | --- |
| 1. | `w3-grayscale-min` | 目标元素的灰度设置为 **50%**。 |
| 2. | `w3-grayscale` | 目标元素的灰度设置为 **75%**。 |
| 3. | `w3-grayscale-max` | 目标元素的灰度设置为 **100%**。 |
| 4. | `w3-hover-grayscale` | 悬停时目标元素的灰度设置为 **100%**。 |

**示例:**

```html
<!DOCTYPE html>
<html>
<head>
    <!-- Adding W3.CSS file through external link -->
    <link rel="stylesheet" href="https://www.w3schools.com/w3css/4/w3.css">
</head>
<body>
    <!-- w3-container is used to add 16px padding to any HTML element. -->
    <!-- w3-center is used to set the content of the element to the center. -->
    <div class="w3-container w3-center">
        <!-- w3-text-green sets the text colour to green. -->
        <!-- w3-xxlarge sets font size to 32px. -->
        <h2 class="w3-text-green w3-xxlarge">Welcome To GFG</h2>
    </div>

    <!-- Images with Grayscale Effects -->
    <div class="w3-row w3-row-padding w3-center">
        <!-- Minimum Grayscale -->
        <div class="w3-col m3 l3">
            <img class="w3-image w3-grayscale-min" src="gfg.png">
            <p>
                <span class="w3-text-red">Class</span><br>
                <span class="w3-text-blue">w3-grayscale-min</span>
            </p>
        </div>
        <!-- Normal Grayscale -->
        <div class="w3-col m3 l3">
            <img class="w3-image w3-grayscale" src="gfg.png">
            <p>
                <span class="w3-text-red">Class</span><br>
                <span class="w3-text-blue">w3-grayscale</span>
            </p>
        </div>
        <!-- Maximum Grayscale -->
        <div class="w3-col m3 l3">
            <img class="w3-image w3-grayscale-max" src="gfg.png">
            <p>
                <span class="w3-text-red">Class</span><br>
                <span class="w3-text-blue">w3-grayscale-max</span>
            </p>
        </div>
        <!-- On Hover Grayscale -->
        <div class="w3-col m3 l3">
            <img class="w3-image w3-hover-grayscale" src="gfg.png">
            <p>
                <span class="w3-text-red">Class</span><br>
                <span class="w3-text-blue">w3-hover-grayscale</span>
            </p>
        </div>
    </div>
</body>
</html>
```

**输出:**

![](img/278a2cc113adbd68a9e840c77e4b8865.png)

## 乌贼（深褐色）效果

有四个乌贼类:

| Sr 号 | 类名 | 描述 |
| --- | --- | --- |
| 1. | `w3-sepia-min` | 目标元素的棕褐色效果设为 **50%**。 |
| 2. | `w3-sepia` | 目标元素的棕褐色效果设置为 **75%**。 |
| 3. | `w3-sepia-max` | 目标元素的棕褐色效果设置为 **100%**。 |
| 4. | `w3-hover-sepia` | 悬停时目标元素的乌贼效果设置为 **100%**。 |

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>

    <!-- Adding W3.CSS file through external link -->
    <link rel="stylesheet" href=
        "https://www.w3schools.com/w3css/4/w3.css">
</head>

<body>
    <!-- w3-container is used to add 16px 
        padding to any HTML element.  -->
    <!-- w3-center is used to set the content 
        of the element to the center. -->
    <div class="w3-container w3-center">

        <!-- w3-text-green sets the text 
            colour to green. -->
        <!-- w3-xxlarge sets font size to 32px. -->
        <h2 class="w3-text-green w3-xxlarge">
            Welcome To GFG
        </h2>
    </div>

    <!-- Images with Sepia Effects -->
    <div class="w3-row w3-row-padding w3-center">
        <!-- Minimum Sepia -->
        <div class="w3-col m3 l3">
            <img class="w3-image w3-sepia-min" 
                src="gfg.png">

            <p>
                <span class="w3-text-red">Class</span>
                <br>
                <span class="w3-text-blue">
                    `w3-sepia-min`
                </span>
            </p>

        </div>
        <!-- Normal Sepia -->
        <div class="w3-col m3 l3">
            <img class="w3-image w3-sepia" 
                src="gfg.png">

            <p>
                <span class="w3-text-red">Class</span>
                <br>
                <span class="w3-text-blue">
                    `w3-sepia`
                </span>
            </p>

        </div>
        <!-- Maximum Sepia -->
        <div class="w3-col m3 l3">
            <img class="w3-image w3-sepia-max"
                src="gfg.png">

            <p>
                <span class="w3-text-red">Class</span>
                <br>
                <span class="w3-text-blue">
                    `w3-sepia-max`
                </span>
            </p>

        </div>
        <!-- On Hover Sepia -->
        <div class="w3-col m3 l3">
            <img class="w3-image w3-hover-sepia"
                src="gfg.png">

            <p>
                <span class="w3-text-red">Class</span>
                <br>
                <span class="w3-text-blue">
                    `w3-hover-sepia`
                </span>
            </p>
        </div>
    </div>
</body>

</html>
```

输出:

![](img/7f9e95ab31b75ab1fae9774ef086aad7.png)