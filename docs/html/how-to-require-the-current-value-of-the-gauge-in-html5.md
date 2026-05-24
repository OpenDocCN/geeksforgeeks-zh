# html 5 中如何要求仪表的当前值？

> 原文:[https://www . geesforgeks . org/how-to-require-the-current-value-of-gauge-in-html 5/](https://www.geeksforgeeks.org/how-to-require-the-current-value-of-the-gauge-in-html5/)

一个**仪表**是一个标记，可以是刻度盘或条的形式。它具有*最小、最大、高*和*低*属性来显示提供给它的数据量。

在 HTML5 中 [<仪表>](https://www.geeksforgeeks.org/html-meter-high-attribute/#:~:text=Related%20Articles&text=The%20HTML%20high%20Attribute%20is,with%20the%20Element.) 标签用于以仪表的形式显示和测量给定范围内的数据。以下属性与 HTML5 中的 *<仪表>* 标签一起使用。

**语法:**

> <meter min_value="”value”" low_value="”value”" high_value="”value”" max_value="”value”">current _ value =“value”</meter>

**示例:**以下示例演示了如何在 HTML5 中获取仪表的当前值。在代码中，为属性设置了以下值。

*   *分钟*值设置为 0
*   *最大* 值设置为 100
*   将*低* 值设置为 10
*   将*高* 值设置为 90
*   学生的*当前*值/分数在*值* 属性中指定。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
</head>
<body>
    <h2 style="color:green">GeeksforGeeks </h2>
    <p> 
    <b>The scores of the students: </b> 
    </p>

    <p>
    A:
    <meter min="0" low="10" high="90" 
           max="100" value="40"></meter>
    </p>

    <p>
    B:
    <meter min="0" low="10" high="90" 
           max="100" value="70"></meter>
    </p>

    <p>
    C:
    <meter min="0" low="10" high="90" 
           max="100" value="45"></meter>
    </p>

    <p>
    D:
    <meter min="0" low="10" high="90"
           max="100" value="90"></meter>
    </p>

    <p>
    E:
    <meter min="0" low="10" high="90" 
           max="100" value="55"></meter>
    </p>

    <p>
    F:
    <meter min="0" low="10" high="90" 
           max="100" value="96"></meter>
    </p>

</body>
</html>
```

**输出:**如果数值(当前)大于高值或小于低值，仪表中的条显示*黄色***T5。如果数值(当前)在低值和高值之间，仪表中的条显示一种*绿色* 颜色。**

![](img/4a628067b388c3447c5764217c7be1b4.png)

仪表值