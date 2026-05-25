# 什么是 Bootstrap 4 中的图像缩略图？

> 原文：[`https://www.geeksforgeeks.org/what-is-image-thumbnail-in-bootstrap-4/`](https://www.geeksforgeeks.org/what-is-image-thumbnail-in-bootstrap-4/)

使用 [`<img>`](https://www.geeksforgeeks.org/html-img-tag/) 标签显示 [Bootstrap 4](https://www.geeksforgeeks.org/bootstrap-4-introduction/) 中的图像。在 Bootstrap 中，缩略图是图像周围的边框。它是使用 `img-thumbnail` 类创建的。

## 语法

```html
<img src="..." alt="...">
```

## 图像缩略图

在 Bootstrap 4 中，图像缩略图是被图像包围的边界。要创建此图像缩略图，您可以使用 `img-thumbnail` 类。

### 语法

```html
<img src="..." alt="..." class="img-thumbnail">
```

## 示例

### HTML

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <meta name="viewport"
          content="width=device-width, initial-scale=1">
    <link rel="stylesheet" 
          href="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js">
    </script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.16.0/umd/popper.min.js">
    </script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js">
    </script>
</head>

<body style="background-color:black">
    <center>
        <h1 style="color:green;">
          GeeksforGeeks
        </h1>
        <div class="container">
            <h2 style="color:white">
              Thumbnail
            </h2> 
          <img src="https://media.geeksforgeeks.org/wp-content/uploads/20210929144017/geeksimage-200x145.png" 
               class="img-thumbnail" 
               alt="GFG" 
               width="200" 
               height="200"> 
      </div>
    </center>
</body>

</html>
```

## 输出

![](img/b2b1004b29c501011ead66ae1fd4e45c.png)