# 如何使用 datetimepicker 库设置 Bootstrap Timepicker？

> 原文：[https://www.geeksforgeeks.org/how-to-set-bootstrap-timepicker-using-datetimepicker-library/](https://www.geeksforgeeks.org/how-to-set-bootstrap-timepicker-using-datetimepicker-library/)

在本文中，我们将看到如何使用引导数据库日期选择器插件来实现日期选择器，以便使用 `jQuery` 选择日期和时间。默认情况下，选择今天的日期。`DateTimePicker` 有各种可配置的选项，可以根据需要使用 `DateTimePicker`。在本教程中，我们将看到如何使用引导数据库日期选择器插件来选择日期和时间来实现日期选择器。

## `DateTimePicker` 有以下视图：

*   十年视图
*   年度视图
*   月视图
*   日视图
*   小时视图
*   带子午线的日景
*   带子午线的小时视图

## `DateTimePicker` 可以通过以下方式进行格式化：

*   `yyyy-mm-dd`
*   `yyy-mm-dd hh:ii`
*   `yyyy-mm-ddThh：ii`
*   `yyy-mm-dd hh:ii:ss`
*   `yyyy-mm-ddThh:ii:ssZ`

## `DateTimePicker` 格式

默认格式为字符串 `'mm/DD/yyyy'`。

<figure class="table">

| format | explain | Example (6/7/2021 06:02:09) |
| --- | --- | --- |
| **d** | Displays the day of the month without leading zeros. | six |
| **DD** | Displays the day of the month with leading zeros. | 07 |
| **yy** | Display year in two-digit format. | 21 |
| **YYYY** | Displays the year in four-digit format. | 2021 |
| **A** | AM or PM. | AM |
| **SS** | Displays the number of the seconds with leading zeros. | 09 |
| **m** | Displays the number of the month without leading zeros. | 6 |
| **mm** | Displays the number of the month with leading zeros. | 06 |

</figure>

## 设置日期选择器：

### 第一步：在所有其他样式表加载我们的 CSS 之前，将 `Bootstrap` 和 `jQuery` CDN 包含到你的 `<head>` 中。

```html
<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.9.1/jquery.js"></script>
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js"></script>
```

### 第二步：在引导 CSS CDN 之后包含 `DateTimePicker` JS 和 CSS CDN。

```html
<link href="https://cdnjs.cloudflare.com/ajax/libs/bootstrap-datetimepicker/4.17.37/css/bootstrap-datetimepicker.min.css" rel="stylesheet">
<script src="https://cdnjs.cloudflare.com/ajax/libs/bootstrap-datetimepicker/4.17.37/js/bootstrap-datetimepicker.min.js"></script>
```

### 第三步：将下面的代码包含在 `<body>` 中，接受用户的时间。

```html
<div class="container" style="margin: 50px">
   <div style="position: relative">
       <input class="form-control" type="text" id="time"/>
   </div>
</div>
```

**注意：** `DateTimePicker` 组件应始终放置在相对定位的容器中。

### 第四步：在 `<body>` 标签后添加 `<script>` 标签中的以下 `JavaScript`，指定 `"HH:mm:ss"` 格式为 `DateTimePicker`。

```javascript
$('#time').datetimepicker({
    format: 'yyyy-mm-dd'
});
```

**注：** 可根据需要指定自定义格式。

## 示例

```html
<!DOCTYPE html>
<html>

<head>
    <title>DateTimepicker</title>

    <!-- Include Bootstrap CDN -->
    <link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css" rel="stylesheet">
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.9.1/jquery.js"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js"></script>

    <!-- Include Moment.js CDN -->
    <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/moment.js/2.9.0/moment.min.js"></script>

    <!-- Include Bootstrap DateTimePicker CDN -->
    <link href="https://cdnjs.cloudflare.com/ajax/libs/bootstrap-datetimepicker/4.17.37/css/bootstrap-datetimepicker.min.css" rel="stylesheet">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/bootstrap-datetimepicker/4.17.37/js/bootstrap-datetimepicker.min.js"></script>
</head>

<body>

    <!-- Include datetime input to display datetimepicker in container with relative position -->
    <div class="container" style="margin:100px">
        <div style="position: relative">
            <!-- Include input field with id so that we can use it in JavaScript to set attributes.-->
            <input class="form-control" type="text" id="datetime" />
        </div>
    </div>

    <script>
        // Below code sets format to the datetimepicker having id as datetime
        $('#datetime').datetimepicker({
            format: 'hh:mm:ss a'
        });
    </script>
</body>

</html>
```

## 输出

![](img/c94800dcc1b143effa886f8ded56272e.png)