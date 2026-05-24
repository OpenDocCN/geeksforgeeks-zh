# SVG 半径属性

> 原文:[https://www.geeksforgeeks.org/svg-radius-attribute/](https://www.geeksforgeeks.org/svg-radius-attribute/)

**半径**属性是在 *<女性形态>* 滤镜图元上进行操作的半径。如果给定两个数，那么第一个数是 x 半径，第二个数是 y 半径。如果只给出一个数字，那么它将用于 x 轴和 y 轴。

**注意:**零或负值禁用 *<女性形态>* 滤镜图元的效果。

**语法:**

```html
radius = number-optional-number

```

**属性值:**半径属性接受上面提到的和下面描述的值:

*   **数字-可选-数字:**是一对数字，其中第二个数字是可选的。其默认值为 0。

以下示例说明了 radius 属性的使用。

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        text {
            font-family: Arial;
            font-size: 2.5em;
        }
    </style>
</head>

<body>
    <div style="color: green;">
        <h1>
            GeeksforGeeks
        </h1>

        <svg xmlns="http://www.w3.org/2000/svg">

            <filter id="Geek1">
                <feMorphology operator="erode" 
                    radius=".5" />
            </filter>
            <text style="filter: url(#Geek1);" 
                y="1em">Thin Geeky Text</text>
        </svg>
    </div>
</body>

</html>
```

**输出:**

![](img/8c5a031f81394ae89ef6f1261e42acfc.png)

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        text {
            font-family: Arial;
            font-size: 2em;
        }
    </style>
</head>

<body>
    <div style="color: green;">
        <h1>
            GeeksforGeeks
        </h1>

        <svg xmlns="http://www.w3.org/2000/svg">

            <filter id="Geek1">
                <feMorphology operator="dilate"
                        radius="2" />
            </filter>
            <text style="filter: url(#Geek1);" 
                y="1em">Thick Geeky Text</text>
        </svg>
    </div>
</body>

</html>
```

**输出:**

![](img/8c757820c508422658bcc8dc3d9a44e0.png)