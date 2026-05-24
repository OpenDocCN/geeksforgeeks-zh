# 解释引导

中的基本表格

> 原文:[https://www . geesforgeks . org/explain-the-basic-in-table-bootstrap/](https://www.geeksforgeeks.org/explain-the-basic-table-in-bootstrap/)

[Bootstrap](https://www.geeksforgeeks.org/bootstrap-tutorials/) 提供了各种不同风格和颜色的桌子，有些桌子采用了响应性设计，有些桌子则采用了悬浮效果。不同的类可以用于不同的表格样式，或者在 bootstrap 中启用它的各种功能，如表格压缩、更改标题外观等。根据用户偏好使用这些类来获得所需的外观。

**基本引导表:**使用**可以创建基本引导表。表**类中的表标签的 HTML 代码。它几乎没有造型，只有水平分隔。我们还可以给桌子增加一些风格，让它看起来更有吸引力。

**为 bootstrap 表格设置样式:**在 Bootstrap 中为表格设置样式的其他一些类有:

*   **Table border:** It is used to add borders to tables and cells.
*   **Table-Condensation:** It cuts the cell padding in half, making the table more compact and compressed.
*   **Table-Dark:** This class is used to change the background color of the table to black.
*   **Table-Hover:** Enable the hover function of table rows.
*   **Table Response:** is used to create a response table, that is, the table can dynamically change its appearance according to the viewed screen.

以下是使用基本引导表的步骤。

**步骤 1:** 在代码中包含以下样式表链接，为表格添加基本样式，即水平分隔线和填充。

> < link rel= "样式表" href = " https://maxcdn . bootstrapcdn . com/bootstrap/4 . 3 . 1/CSS/bootstrap . min . CSS ">

**第二步:**添加类，**。表**中的<表>标记。

**语法:**

```html
<table class="table"> 
    <thead>
        <tr>
            <th scope="col">S. No.</td>
            <th scope="col">Topic</td>
            <th scope="col">Problems</td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <th scope="row">1</td>
            <td>Array</td>
            <td>400</td>
        </tr>
    </tbody>
</table>
```

**示例 1:** 在本例中，我们将使用上述步骤创建一个基本的引导表。

index.html