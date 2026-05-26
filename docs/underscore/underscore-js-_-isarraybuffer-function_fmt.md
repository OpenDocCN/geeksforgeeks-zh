# 下划线.js _.isArrayBuffer()函数

> 原文: [https://www.geeksforgeeks.org/underscore-js-_-isarraybuffer-function/](https://www.geeksforgeeks.org/underscore-js-_-isarraybuffer-function/)

下划线.js 是一个 JavaScript 库，它提供了许多有用的函数，这些函数在很大程度上有助于编程，比如映射、过滤、调用等，甚至不使用任何内置对象。

`_.isArrayBuffer()` 函数是一个内置在下划线.js JavaScript 库中的函数，用于检查所述对象是否为 `ArrayBuffer`。

## 语法:

```
_.isArrayBuffer(object)
```

## 参数:

它接受以下指定的单个参数:

*   `object`: 是陈述的对象。

## 返回值:

如果所述对象是 `ArrayBuffer`，则该方法返回 `true`，否则返回 `false`。

## 例 1:

```
<!DOCTYPE html>
<html>

<head>
    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/underscore.js/1.11.0/underscore-min.js">
    </script>
</head>

<body>
    <script>
        console.log(_.isArrayBuffer(
            new ArrayBuffer(3, 4, 6, 4)));
    </script>
</body>

</html>
```

**输出:**

```
true
```

## 例 2:

```
<!DOCTYPE html>
<html>

<head>
    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/underscore.js/1.11.0/underscore-min.js">
    </script>
</head>

<body>
    <script>
        console.log(_.isArrayBuffer(
            "GeeksforGeeks", "CS"));
    </script>
</body>

</html>
```

**输出:**

```
false
```

## 参考:

[https://underscorejs.org/#isArrayBuffer](https://underscorejs.org/#isArrayBuffer)