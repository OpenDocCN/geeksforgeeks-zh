# 如何使用 Bootstrap 在 optgroup 标签前添加图像？

> 原文:[https://www . geeksforgeeks . org/如何在 optgroup 之前添加图像-标签-使用-bootstrap/](https://www.geeksforgeeks.org/how-to-add-image-before-optgroup-label-using-bootstrap/)

**什么是 optgroup 标签？**

它是一个 HTML 标签，用于对 **[<中给出的选项进行分组，选择>标签](https://www.geeksforgeeks.org/html-select-tag/)** 。这结合了具有不同标签的不同组中的选项。

**语法:**

```html
<optgroup label="text">
  <option value="One">One</option>
  <option value="Two">Two</option>
</optgroup>
```

如果我们需要使用 bootstrap 在 **optgroup** 标签之前添加一个图像，那么我们必须在标签中放置“image”标签，给出带有标签名称的图像的源位置。

**示例:**以下示例演示了使用 Bootstrap 在标签前具有图像的**光学组**。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, 
        shrink-to-fit=no">

    <script src=
"https://code.jquery.com/jquery-3.5.1.slim.min.js">
    </script>

    <script src=
"https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js">
    </script>

    <link rel="stylesheet" href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/css/bootstrap.min.css">

    <script src=
"https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/js/bootstrap.min.js">
    </script>

    <link rel="stylesheet" href=
"https://cdn.jsdelivr.net/npm/bootstrap-select@1.13.14/dist/css/bootstrap-select.min.css">

    <script src=
"https://cdn.jsdelivr.net/npm/bootstrap-select@1.13.14/dist/js/bootstrap-select.min.js">
    </script>

    <style>
        .bootstrap-select img {
            width: 16px;
        }
    </style>
</head>

<body>
    <select class="selectpicker">
        <optgroup label=
"<img src='https://openmoji.org/data/color/svg/1F600.svg'> Numbers">
            <option value="1">One</option>
            <option value="2">Two</option>
            <option value="3">Three</option>
        </optgroup>
        <optgroup label=
"<img src='https://openmoji.org/data/color/svg/1F923.svg'> Digits">
            <option value="Four">4</option>
            <option value="Five">5</option>
            <option value="Six">6</option>
        </optgroup>
    </select>

    <script>
        $('.selectpicker').on('shown.bs.select', function () {
            $('.bootstrap-select .dropdown-header').each(function () {
                if ((this.dataset.unescaped || '1') == '1') {
                    let element = $(this);
                    element.html(element.text());
                    element.attr('data-unescaped', '0');
                }
            })
        })
    </script>
</body>

</html>
```

![](img/751bc944f0c9594e420c4d4a6ac00e27.png)