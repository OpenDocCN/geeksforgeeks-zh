# 如何在两列都是直的 CSS 中对齐文本？

> 原文:[https://www . geesforgeks . org/如何对齐 css 中的文本-其中两列都是直的/](https://www.geeksforgeeks.org/how-to-align-text-in-css-where-both-columns-are-straight/)

**简介:**要对齐 CSS 中的文本，有很多选项可以选择。基本上，在 CSS 或 HTML 中，列总是直的，但在这里，列是直的意味着列之间的间距和每列的行数应该相等。

**方法:**在 CSS 中，每一列都充当一个方框，因此对齐的工作方式和控制完全取决于**方框对齐**模块，该模块旨在为所有 CSS 创建一致的对齐方法。因此，通过使用**框对齐模块**属性，我们可以对齐两列或两列以上直的文本。通过使用 [CSS 对齐内容属性](https://www.geeksforgeeks.org/css-align-content-property/)

我们可以控制块轴，并通过 [CSS 调整内容属性](https://www.geeksforgeeks.org/css-justify-content-property/)来控制内联轴。但是邮件角色是由 [CSS 列-gap 属性](https://www.geeksforgeeks.org/css-column-gap-property/)扮演的，没有这个属性任务就无法完成。但是只有使用这个属性，我们才能完成任务。

以下示例说明了该方法:

**例 1:**

## 钢性铸铁

```html
<!DOCTYPE html>
<html>
<head>
    <style>
    .gfg {
        -webkit-column-count: 2;
        -moz-column-count: 2;
        column-count: 2;

        -webkit-column-gap: 40px;
        -moz-column-gap: 40px;
        column-gap: 40px; /* Specifying Column Gap */
    }

    h1 {
        color:green;
    }

    h1, h2 {
        text-align:center;
    }
    </style>
</head>

<body>
    <h1>
        GeeksforGeeks
    </h1>

    <!-- Columns with a gap of 40px between
        the columns -->
    <div class="gfg">
        The course is designed for students as well as
        working professionals to prepare for coding
        interviews. This course is going to have coding
        questions from school level to the level
        needed for product based companies like Amazon,
        Microsoft, Adobe, etc.
    </div>
</body>
</html>                    
```

**输出:**

![](img/01db9bf0497b54240a63b61cd02c0e45.png)