# Bootstrap表格基础

> 原文：[https://www.geeksforgeeks.org/explain-the-basic-table-in-bootstrap/](https://www.geeksforgeeks.org/explain-the-basic-table-in-bootstrap/)

[Bootstrap](https://www.geeksforgeeks.org/bootstrap-tutorials/) 提供了各种不同风格和颜色的表格，有些表格采用了响应式设计，有些表格则采用了悬浮效果。不同的类可以用于不同的表格样式，或者在 Bootstrap 中启用它的各种功能，如表格压缩、更改标题外观等。根据用户偏好使用这些类来获得所需的外观。

## 基本引导表

使用 `.table` 类可以创建基本引导表。将 `.table` 类添加到 `<table>` 标签的 HTML 代码中。它几乎没有样式，只有水平分隔线。我们还可以给表格增加一些样式，让它看起来更有吸引力。

## 为 Bootstrap 表格设置样式

在 Bootstrap 中为表格设置样式的其他一些类有：

*   `Table border`：用于为表格和单元格添加边框。
*   `Table-condensed`：将单元格内边距减半，使表格更紧凑。
*   `Table-dark`：此类用于将表格的背景颜色更改为黑色。
*   `Table-hover`：启用表格行的悬停功能。
*   `Table-responsive`：用于创建响应式表格，即表格可以根据查看的屏幕动态改变其外观。

以下是使用基本引导表的步骤。

**步骤 1：** 在代码中包含以下样式表链接，为表格添加基本样式，即水平分隔线和内边距。

```html
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
```

**步骤 2：** 在 `<table>` 标记中添加类 `.table`。

**语法：**

```html
<table class="table"> 
    <thead>
        <tr>
            <th scope="col">S. No.</th>
            <th scope="col">Topic</th>
            <th scope="col">Problems</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <th scope="row">1</th>
            <td>Array</td>
            <td>400</td>
        </tr>
    </tbody>
</table>
```

**示例 1：** 在本例中，我们将使用上述步骤创建一个基本的引导表。

`index.html`