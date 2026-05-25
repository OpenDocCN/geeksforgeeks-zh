# JavaScript Number NEGATIVE_INFINITY 属性

> 原文: [https://www.geeksforgeeks.org/javascript-number-negative_infinity-property/](https://www.geeksforgeeks.org/javascript-number-negative_infinity-property/)

在 JavaScript 中，负数 INFINITY 是数字对象的一个属性，表示负数 infinity (`-Infinity`)。它可以解释为比任何其他数字都低的数字。它是只读属性。

## 语法

`NEGATIVE_INFINITY` 是 `Number` 对象的静态属性，因此总是在引用它时使用

```javascript
Number.NEGATIVE_INFINITY
```

## 返回值

```javascript
-Infinity
```

## 例 1

```html
<!DOCTYPE html>
<html>
<head>
    <title>Number NEGATIVE_INFINITY property
  </title>
</head>
<body>
    <script type="text/javascript">
        var num=100;
        document.writeln(num.NEGATIVE_INFINITY); 
        document.writeln(Number.NEGATIVE_INFINITY);
    </script>
</body>
</html>
```

**输出:**

```text
undefined
-Infinity
```

## 例 2

下面的程序展示了任意一个数乘以负无穷大，本身就是负无穷大。

```html
<!DOCTYPE html>
<html>
<head>
    <title>Number NEGATIVE_INFINITY property
   </title>
</head>
<body>
    <script type="text/javascript">
        var num=100*Number.NEGATIVE_INFINITY;
        document.write(num);
    </script>
</body>
</html>
```

**输出:**

```text
-Infinity
```