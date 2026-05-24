# 用 CSS 创建透明边框

> 原文:[https://www . geeksforgeeks . org/create-a-transparent-border-with-CSS/](https://www.geeksforgeeks.org/create-a-transparent-border-with-css/)

在 **CSS** 中，我们可以通过在嵌套的 **div** 标签中使用**边框**属性来创建透明边框。

**创建这个的步骤是:**
**步骤 1:** 创建一个嵌套的 **[div](https://www.geeksforgeeks.org/div-tag-html/)** 标签。
**步骤 2:** 将外部 **div** 标签的 **[边框样式](https://www.geeksforgeeks.org/css-border-style-property/)** 指定为**实体**，并且 **[边框宽度](https://www.geeksforgeeks.org/css-border-width-property/)** 属性可以是任何所需的大小。
**第三步:**使内 **div** 标签的尺寸小于外 **div** 标签。

或者，我们可以通过使用**边框**简写属性来指定所有单独的属性，如下例所示。

**示例 1:** 使用上述方法在 CSS 中创建透明边框。

```html
<!DOCTYPE html>
<html>

<head>
    <style type="text/css">
        h1 {
            color: green;
        }

        .outer {
            width: 300px;
            height: 300px;
            margin: 10%;
            border: 10px solid rgba(0, 0, 0, .4);
            border-radius: 5px;
        }

        .inner {
            width: 270px;
            height: 270px;
            margin: auto;
            margin-top: 3%;
            text-align: center;
            background: rgba(0, 0, 0, .4);
            border-radius: 5px;
            padding: 5px;
        }
    </style>
</head>

<body>
    <div class="outer">
        <div class="inner">
            <h1>GeeksforGeeks</h1>
        </div>
    </div>
</body>

</html>
```

**输出:**
![](img/3d051fdd23d777dbaaeb089f3bf9c07f.png)

另一种方法是使用单个 **div** 标签，并使用**边框样式的**和**背景剪辑**属性来创建透明边框。

**重现这个的步骤是:**
**步骤 1:** 创建一个 **div** 标签。
**第二步:**将 **[边框样式](https://www.geeksforgeeks.org/css-border-style-property/)** 属性指定为**双**，在框的周围设置两个边框。
**步骤 3:** 将 **[背景-剪辑](https://www.geeksforgeeks.org/css-background-clip-property/)** 属性设置为**填充框**，将背景颜色剪辑到元素的填充中。

**示例 2:** 使用上面讨论的替代方法在 CSS 中创建透明边框。

```html
<!DOCTYPE html>
<html>

<head>
    <style type="text/css">
        h1 {
            color: green;
        }

        .trans_border {
            width: 270px;
            height: 270px;
            margin: auto;
            margin-top: 3%;
            text-align: center;
            border: 20px double rgba(0, 0, 0, .4);
            background: rgba(0, 0, 0, .4);
            background-clip: padding-box;
            border-radius: 5px;
            padding: 5px;
        }
    </style>
</head>

<body>
    <div class="trans_border">
        <h1>GeeksforGeeks</h1>
    </div>
</body>

</html>
```

**输出:**
![](img/087a7f09efd5b3fbd8b2facaadea2a66.png)