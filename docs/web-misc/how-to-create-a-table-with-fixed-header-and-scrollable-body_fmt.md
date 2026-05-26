# 如何创建表头固定、表体可滚动的表？

> 原文：[https://www.geeksforgeeks.org/how-to-create-a-table-with-fixed-header-and-scrollable-body/](https://www.geeksforgeeks.org/how-to-create-a-table-with-fixed-header-and-scrollable-body/)

本文的目的是创建一个具有固定标题和可滚动正文的表。我们可以用这两种方法中的任何一种来创建这样的表。

1.  通过将`position`属性设置为`sticky`，并将`0`指定为`<thead>`元素的`top`属性的值。
2.  通过将`<tbody>`元素的`display`设置为`block`，我们可以将`height`和`overflow`属性应用于`<tbody>`。

**注：**

*   `position`属性表示元素的定位类型。
*   `display`属性说明元素应该如何显示。

## 示例1：使用position属性

下面是说明具有`position`属性的表的形成的代码。

```html
<!DOCTYPE html>
<html>

<head>
  <style>
    .fixTableHead {
      overflow-y: auto;
      height: 110px;
    }
    .fixTableHead thead th {
      position: sticky;
      top: 0;
    }
    table {
      border-collapse: collapse;        
      width: 100%;
    }
    th,
    td {
      padding: 8px 15px;
      border: 2px solid #529432;
    }
    th {
      background: #ABDD93;
    }
  </style>
</head>

<body>
  <div class="fixTableHead">
    <table>
      <thead>
        <tr>
          <th>Col 1</th>
          <th>Col 2</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>1.1</td>
          <td>2.1</td>
        </tr>
        <tr>
          <td>1.2</td>
          <td>2.2</td>
        </tr>
        <tr>
          <td>1.3</td>
          <td>2.3</td>
        </tr>
        <tr>
          <td>1.4</td>
          <td>2.4</td>
        </tr>
        <tr>
          <td>1.5</td>
          <td>2.5</td>
        </tr>
      </tbody>
    </table>
  </div>
</body>

</html>
```

**输出：**

![](img/bdbb76f629187c1fa73f9f69ec215322.png)

## 示例2：使用display属性

下面是用`display`属性说明表格形成的代码。

```html
<!DOCTYPE html>
<html>

<head>
  <style>
    .tableFixHead {
      width: 500px;
      table-layout: fixed;
      border-collapse: collapse;
    }
    .tableFixHead tbody {
      display: block;
      width: 100%;
      overflow: auto;
      height: 50px;
    }
    .tableFixHead thead tr {
      display: block;
    }
    .tableFixHead th,
    .tableFixHead  td {
      padding: 5px 10px;
      width: 200px;
    }
    th {
      background: #ABDD93;
    }
  </style>
</head>

<body>
  <div class="tableFixHead">
    <table>
      <thead>
        <tr>
          <th>Col 1</th>
          <th>Col 2</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>1.1</td>
          <td>2.1</td>
        </tr>
        <tr>
          <td>1.2</td>
          <td>2.2</td>
        </tr>
        <tr>
          <td>1.3</td>
          <td>2.3</td>
        </tr>
        <tr>
          <td>1.4</td>
          <td>2.4</td>
        </tr>
        <tr>
          <td>1.5</td>
          <td>2.5</td>
        </tr>
      </tbody>
    </table>
  </div>
</body>

</html>
```

**输出：**

![](img/0d3596acc0b71118ad1d8600cb8f4908.png)