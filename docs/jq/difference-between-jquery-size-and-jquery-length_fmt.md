# jQuery.size()和jQuery.length的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-jquery-size-and-jquery-length/](https://www.geeksforgeeks.org/difference-between-jquery-size-and-jquery-length/)

`jQuery.size()`方法给我们呈现的元素个数。例如，如果我们为`<p>`标签调用`size()`方法，那么它将返回我们页面上出现的`<p>`标签的数量。

## 语法

```html
$(selector).size()
```

**返回值：** 返回当前“选择器”的个数。

## 示例

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <!-- Using jquery v1.6 library -->
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.6.1/jquery.min.js">
    </script>
</head>

<body>
    <p>para-1</p>
    <p>para-2</p>
    <p>para-3</p>
    <p>para-4</p>
    <p>para-5</p>

<script>
        console.log($("p").size())
    </script>
</body>

</html>
```

## 输出

```html

```

**注意：** 这个方法在 jQuery 3.0 中已经去掉了。因此，上述代码在最新版本的 jQuery 中无法工作。现在，你必须使用`length`属性。

## jQuery.size()实现

```html
size()->function()
{
  return this.length; 
}
```

在这里，我们可以清楚地看到`size()`方法内部调用的是`length`属性。因此，很明显，当我们必须找到元素的大小时，我们可以直接调用的`length`属性，而不是调用方法。

## jQuery.length属性

`jQuery.length`属性比`jQuery.size()`快，因为这里我们没有调用任何函数。

### 语法

```html
$(selector).length
```

**返回值：** 返回选择器的长度。

### 示例

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <!-- using jquery library -->
    <script src="https://code.jquery.com/jquery-git.js">
    </script>
</head>

<body>
    <p>para-1</p>
    <p>para-2</p>
    <p>para-3</p>
    <p>para-4</p>
    <p>para-5</p>

<script>
        console.log($("p").length)
    </script>
</body>

</html>
```

### 输出

```html

```

## jQuery.size()与jQuery.length的区别

| `jQuery.size()`方法 | `jQuery.length`属性 |
| --- | --- |
| It is a method type. | Is an attribute type. |
| It returns the number of elements. | Returns the same number of elements. |
| Internal length attribute. | It does not call any other properties. |
| It is slow because of the cost function. | Just be quick. |
| Was removed in jQuery 3.0. | This is recommended. |