# jQuery insertBefore() 方法详解与示例

> 原文：[https://www.geeksforgeeks.org/jquery-insertbefore-with-examples/](https://www.geeksforgeeks.org/jquery-insertbefore-with-examples/)

`insertBefore()` 是 jQuery 中的一个内置方法，用于在指定的元素前插入一些 HTML 内容。HTML 内容将在指定元素的每次出现之前插入。

## 语法

```html
$(content).insertBefore(target)
```

这里的 `content` 是需要在指定目标之前插入的 HTML 内容。

## 参数

它接受一个参数 `target`，该参数是内容要插入的目标。

## 返回类型

不返回值。

## jQuery 代码示例：展示 insertBefore() 方法的工作原理

### 代码 #1

```html
<!DOCTYPE html>
<html>

<head>
    <script 
    src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
    <script>
        $(document).ready(function() {
            $("div").click(function() {
                // insertBefore
                $("<p>You should follow GeeksForGeeks</p>").insertBefore("p");
            });
        });
    </script>
</head>

<body>

<p>To learn jQuery </p>

<div>Click here to complete</div>

</body>

</html>
```

### 输出

点击 div 内容前：

```html
To learn jQuery
Click here to complete
```

点击 div 内容后：

```html
You should follow GeeksForGeeks
To learn jQuery 
Click here to complete
```

### 代码 #2

```html
<!DOCTYPE html>
<html>

<head>
    <script 
    src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
    <script>
        $(document).ready(function() {
            $("div").click(function() {
                // insertBefore
                $("<p>You should follow GeeksForGeeks</p>").insertBefore("p");
            });
        });
    </script>
</head>

<body>

<p>To learn jQuery </p>

<p> To learn coding </p>

<div>Click here to complete</div>

</body>

</html>
```

### 输出

点击 div 内容前：

```html
To learn jQuery 
To learn coding 
Click here to complete
```

点击 div 内容后：

```html
You should follow GeeksForGeeks
To learn jQuery 
You should follow GeeksForGeeks
To learn coding
Click here to complete
```