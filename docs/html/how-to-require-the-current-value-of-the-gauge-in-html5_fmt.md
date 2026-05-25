# HTML5 中如何获取仪表的当前值？

> 原文：[https://www.geeksforgeeks.org/how-to-require-the-current-value-of-the-gauge-in-html5/](https://www.geeksforgeeks.org/how-to-require-the-current-value-of-the-gauge-in-html5/)

一个**仪表**是一个标记，可以是刻度盘或条的形式。它具有`min`、`max`、`high`和`low`属性来显示提供给它的数据量。

在 HTML5 中，`<meter>` 标签用于以仪表的形式显示和测量给定范围内的数据。以下属性与 HTML5 中的 `<meter>` 标签一起使用。

**语法：**

```
<meter min="value" low="value" high="value" max="value">current_value = "value"</meter>
```

**示例：** 以下示例演示了如何在 HTML5 中获取仪表的当前值。在代码中，为属性设置了以下值。

*   `min` 值设置为 0
*   `max` 值设置为 100
*   `low` 值设置为 10
*   `high` 值设置为 90
*   学生的当前值/分数在 `value` 属性中指定。

## HTML 代码

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

**输出：** 如果数值（当前）大于 `high` 值或小于 `low` 值，仪表中的条显示**黄色**。如果数值（当前）在 `low` 值和 `high` 值之间，仪表中的条显示一种**绿色**颜色。

![](img/4a628067b388c3447c5764217c7be1b4.png)

仪表值