# _.isArguments()

> 原文：[https://www.geeksforgeeks.org/underscore-js-_-isarguments-function/](https://www.geeksforgeeks.org/underscore-js-_-isarguments-function/)

`_.isArguments()`函数用于检查给定的对象是否是参数。如果给定对象是参数，则返回布尔值`true`，否则返回`false`。

## 语法

```
_.isArguments( object )
```

## 参数

该函数接受一个参数，如下所述：

*   **对象：** 该参数保存需要检查是否是参数的对象的值。

## 返回值

如果给定对象是参数，则返回`true`，否则返回`false`。

## 例 1

```
<!DOCTYPE html>
<html>

<head>
    <script type="text/javascript" src=
"https://cdnjs.cloudflare.com/ajax/libs/underscore.js/1.9.1/underscore-min.js">
    </script>
</head>

<body>
    <script type="text/javascript">

var arg = (function () {
            return _.isArguments(arguments);
        })('Welcome', 'to', 'GeeksforGeeks');

console.log(arg);
    </script>
</body>

</html>
```

输出：
![](img/b1bb18c0a22ecf4785988068894395d6.png)

## 例 2

```
<!DOCTYPE html>
<html>

<head>
    <script type="text/javascript" src=
"https://cdnjs.cloudflare.com/ajax/libs/underscore.js/1.9.1/underscore-min.js">
    </script>
</head>

<body>
    <script type="text/javascript">

console.log(_.isArguments(true));
        console.log(_.isArguments(1));
        console.log(_.isArguments('GeeksforGeeks'));
        console.log(_.isArguments([1, 2, 3]));
    </script>
</body>

</html>
```

输出：
![](img/80ad45ccfe8e304ae00c113f0277610c.png)