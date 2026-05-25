# jQuery `hover()` 方法详解与示例

> 原文：`https://www.geeksforgeeks.org/jquery-hover-with-examples/`

`hover()` 是 jQuery 中的一个内置方法，用于指定当鼠标指针移动到所选元素上时触发的两个函数。

## 语法

```html
$(selector).hover(Function_in, Function_out);
```

这里 `selector` 是被选择的元素。

## 参数

该方法接受以下两个指定的参数：

*   `Function_in`：指定鼠标进入事件发生时要运行的函数。
*   `Function_out`：可选，指定鼠标离开事件发生时要运行的函数。

## 返回值

返回选中元素的背景色效果。

## jQuery 代码展示 `hover()` 的工作方式

### 代码示例 #1

```html
<html>

<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
    <script>
        <!-- jQuery code to show the working of hover() method -->
        $(document).ready(function() {
            $("p").hover(function() {
                $(this).css("background-color", "green");
            }, function() {
                $(this).css("background-color", "yellow");
            });
        });
    </script>
    <style>
        p {
            width: 55%;
            height: 80px;
            padding: 20px;
            margin: 10px;
            border: 2px solid green;
            font-size: 50px;
        }
    </style>
</head>

<body>
    <!--move the mouse in and out over this paragraph
        and background color will change-->
    <p>GeeksforGeeks !</p>

</body>

</html>
```

## 输出

鼠标指针移至段落上之前：
![](img/f01081fe26003c4e8b23c2fc6a620c52.png)

鼠标指针移至段落上之后：
![](img/01a53ae417605cf82d0b003417528368.png)

鼠标指针移出段落之后：
![](img/61616bff348d35ecef557d690098eb58.png)