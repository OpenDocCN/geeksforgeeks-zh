# 织物 `min()` 方法

> 原文: [https://www.geeksforgeeks.org/fabric-js-min-method/](https://www.geeksforgeeks.org/fabric-js-min-method/)

`min()` 方法用于从指定数组中寻找最小值。

## 语法

```
min( array )
```

## 参数

该方法接受如上所述的单个参数，描述如下:

*   `Array`: 此参数持有要迭代的数组。

## 返回值

该方法从数组中返回最小值。

## 示例 1

```javascript
<!DOCTYPE html>
<html>

<head>
    <!-- Loading the FabricJS library -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/fabric.js/3.6.2/fabric.min.js"></script>
</head>

<body>
    <script type="text/javascript">
        console.log(fabric.util.array.min([5, 3, 9, 2]));
    </script>
</body>

</html>
```

**输出:**

```
2
```

## 示例 2

在下面的代码中，字母表的 ASCII 值被考虑用于查找最小值。

```javascript
<!DOCTYPE html>
<html>

<head>
    <!-- Loading the FabricJS library -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/fabric.js/3.6.2/fabric.min.js"></script>
</head>

<body>
    <script type="text/javascript">
        console.log(fabric.util.array.min(["a", "gfg"]));
    </script>
</body>

</html>
```

**输出:**

```
a
```

## 参考

[http://fabricjs.com/docs/fabric.util.array.html#.min](http://fabricjs.com/docs/fabric.util.array.html#.min)