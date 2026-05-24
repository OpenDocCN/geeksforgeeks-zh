# 如何在 Bootstrap 中创建五个相等的列？

> 原文：[https://www.geeksforgeeks.org/how-to-create-five-equal-columns-in-bootstrap/](https://www.geeksforgeeks.org/how-to-create-five-equal-columns-in-bootstrap/)

在行中创建任意数量的相等列从来没有像现在的 Bootstrap 4.0+ 这样容易。随着 `flexbox` 方法在网格系统中的引入，设计人员不必担心添加额外的 CSS 来使其工作。事情是这样的。

## Approach:

*   转到引导网站，将最新的引导文件下载到您的计算机上。
*   使用这些文件编写一个基本的 HTML 模板。
*   一旦一切就绪，在 `<body>` 标签内创建一个简单的 `container` div。
*   Inside the `container`，创建另一个 div，类为 `row`，顾名思义，我们正在创建一个用于处理列的行。用 5 个类为 `col` 的 div 填充 `row` div。因为 Bootstrap 4.0+ 网格系统现在已转向 Flexbox，列将自行排列成五个大小相等的 DOM 元素。

## 示例：

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <meta name="viewport"
          content="width=device-width, initial-scale=1, shrink-to-fit=no">
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css" />
    <title>5 cols a row</title>
    <style>
        .row .col {
            height: 100px;
            background: green;
        }
    </style>
</head>
<body>
    <div class="container px-5 py-5">
        <div class="row">
            <div class="col mx-1">1</div>
            <div class="col mx-1">2</div>
            <div class="col mx-1">3</div>
            <div class="col mx-1">4</div>
            <div class="col mx-1">5</div>
        </div>
    </div>
    <script src="https://code.jquery.com/jquery-3.2.1.slim.min.js"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js"></script>
</body>
</html>
```

*为了区分各列，每个列都添加了一个小边距。*

**输出：**
![](img/97037fc2a92a9ea0ea2c8f8351bea688.png)