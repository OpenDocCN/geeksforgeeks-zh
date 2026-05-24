# 如何在 Bootstrap 中更改窗体控件的大小？

> 原文：[https://www.geeksforgeeks.org/how-to-change-the-size-of-form-controls-in-bootstrap/](https://www.geeksforgeeks.org/how-to-change-the-size-of-form-controls-in-bootstrap/)

引导允许使用 [`form-control`](https://www.geeksforgeeks.org/bootstrap-part-4/) 类来改变表单控件的大小。对于默认尺寸，使用 `form-control`。对于较小的尺寸，我们可以使用 `form-control` 类和 `form-control-sm` 类。对于更大的尺寸，我们可以使用 `form-control` 类和 `form-control-lg` 类。

## 语法：

### 默认尺寸：

```html
class="form-control"
```

### 小尺寸：

```html
class="form-control form-control-sm"
```

### 对于大尺寸：

```html
class="form-control form-control-lg"
```

## 方法：

在所有其他样式表之前，将 Bootstrap 和 jQuery CDN 包含到 `<head>` 标签中，以加载我们的 CSS。

```html
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.16.0/umd/popper.min.js"></script>
```

添加 `form-control` 类为默认大小，`form-control-sm` 用于小型表单控件和 `form-control-lg` 对于大尺寸表单控件，使用 [`<input>`](https://www.geeksforgeeks.org/html-input-tag/) 标记。

```html
<input class="form-control form-control-lg" type="text" placeholder=".form-control-lg" aria-label=".form-control-lg example">
<input class="form-control" type="text" placeholder="Default input" aria-label="Default input example">
<input class="form-control form-control-sm" type="text" placeholder=".form-control-sm" aria-label=".form-control-sm example">
```

## 示例：

```html
<!DOCTYPE html>
<html>
   <head>
      <title>Bootstrap Form Control Size Example</title>
      <!--Include Latest Bootstrap, jQuery and CSS CDN -->
      <link rel="stylesheet"
            href="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
      <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js">
     </script>
      <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.16.0/umd/popper.min.js">
     </script>
      <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js">
     </script>
   </head>
   <body style="padding:100px;">
     <!-- Add class .form-control-lg after
     .form-control to display large size form control-->
     <input class="form-control form-control-lg"
            type="text"
            placeholder=".form-control-lg"
            aria-label=".form-control-lg example">
     <br>
      <!-- Add class .form-control to display
          default size form control-->
     <input class="form-control" type="text"
            placeholder="Default input"
            aria-label="default input example">
     <br>
      <!-- Add class .form-control-sm after
          .form-control to display small form control-->
     <input class="form-control form-control-sm"
            type="text"
            placeholder=".form-control-sm"
            aria-label=".form-control-sm example">
   </body>
</html>
```

## 输出：

![](img/3a16b0380e3a7dc5915820e257c9c9ac.png)