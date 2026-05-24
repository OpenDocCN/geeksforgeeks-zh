# 如何在 Bootstrap 中制作进度条动画？

> 原文：[https://www.geeksforgeeks.org/how-to-animate-a-progress-bar-in-bootstrap/](https://www.geeksforgeeks.org/how-to-animate-a-progress-bar-in-bootstrap/)

`Bootstrap`进度条是`Bootstrap`框架的一个组件，用于显示流程的进度。我们可以根据需要自定义`Bootstrap`进度条、颜色、形状和动画。`Bootstrap`还提供了几种类型的进度条。

使用进度条，用户可以很容易地了解特定流程的工作状态。例如，如果用户正在下载文件，进度条可以用来显示正在进行的下载的进度，上传等也是如此。

## 进度条动画制作分步指南

### 步骤 1

将`Bootstrap`和`jQuery` `CDN`包含到所有其他样式表之前的`<头>`标签中，以加载我们的`CSS`。

```html
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.16.0/umd/popper.min.js"></script>
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>
```

### 第二步

用*类*添加一个`HTML` [`<div>`](https://www.geeksforgeeks.org/div-tag-html/)。`进度`*和*`进度条纹`。还增加类`激活`至`进度条纹`。在`<div>`里面添加一个空的`<div>`带类的`进度条`和`进度条-成功`。使用`CSS`属性指定进度条的宽度。

```html
<div class="progress progress-striped active">
    <div class="progress-bar progress-bar-success"
        style="width:0%">
    </div>
</div>
```

### 第三步

在`<脚本>`标签中添加`jQuery`，使进度条动画化，显示进度。

```javascript
$(".progress-bar").animate({
    width: "70%"
}, 2500);
```

## 示例

```html
<!DOCTYPE html>
<html>

<head>
    <title>Bootstrap Progress Bar Animation Example</title>

    <!--Include Latest compiled and minified CSS -->
    <link href="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" rel="stylesheet" />
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.16.0/umd/popper.min.js"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>
</head>

<body>
    <br><br>

    <!--Include bootstrap progress bar in div. 
        Also specify width as 0% using CSS -->
    <div class="progress progress-striped active">
        <div class="progress-bar progress-bar-success" style="width: 0%"></div>
    </div>

    <script>
        // Set the width to animate the progress bar
        // Along with time duration in milliseconds
        $(".progress-bar").animate({
            width: "70%",
        }, 2500);
    </script>
</body>

</html>
```

## 输出

![](img/fd0ae64b942e5dbe58ab0c301b843b9d.png)