# 引导图|带示例的图形类

> 原文:[https://www . geesforgeks . org/bootstrap-figure-class-with-examples/](https://www.geeksforgeeks.org/bootstrap-figure-class-with-examples/)

当需要显示一段内容时，使用**图形**，通常是带有可选标题的图像。Bootstrap 中的图形类用于为默认图形元素添加样式。

*   基础**。图**类用于表示一个图元素。
*   **。图-img** 用于指示图元素中使用的图像。
*   **。图形-标题**可用于在图形下方显示标题。

**示例**:使用**。图**类带样本图像。

```html
<!DOCTYPE html>
<html>
<head>
    <!-- Including Bootstrap CSS -->
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css">
    <title>Figures in Bootstrap</title>
</head>

<body>
    <div class="container">
        <h1>Figures in Bootstrap</h1>
        <figure class="figure">
            <img class="figure-img" src="https://media.geeksforgeeks.org/wp-content/uploads/sample_image.png" >
        </figure>
</body>
</html>                    
```

**输出:**
![figure without caption](img/7255afbba0ca86f513fc5fdbc6a53d8c.png)

**示例**:使用**。图-标题**类在图像下方显示标题。此类与 **< figcaption >** 标签一起使用。

```html
<!DOCTYPE html>
<html>
<head>
    <!-- Add Bootstrap CSS -->
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css">

    <title>Figures in Bootstrap</title>
</head>

<body>
    <div class="container">
        <h1>Figures in Bootstrap</h1>

        <figure class="figure">
            <img class="figure-img" src= "https://media.geeksforgeeks.org/wp-content/uploads/sample_image.png" >

            <figcaption class="figure-caption">
                Caption for the above image.
            </figcaption>
        </figure>
</body>
</html>                    
```

**输出:**
![figure with caption](img/d7ea2e18db41fa22ea1959615fc17bcf.png)

**参考**:[https://getbootstrap.com/docs/4.0/content/figures/](https://getbootstrap.com/docs/4.0/content/figures/)