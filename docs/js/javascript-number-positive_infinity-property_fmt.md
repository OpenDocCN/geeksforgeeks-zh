# JavaScript Number.POSITIVE_INFINITY 属性

> 原文: [https://www.geeksforgeeks.org/javascript-number-positive_infinity-property/](https://www.geeksforgeeks.org/javascript-number-positive_infinity-property/)

下面是 `Number.POSITIVE_INFINITY` 属性的示例。

**例:**

```javascript
<script>
var a = Number.POSITIVE_INFINITY;
document.write(a * 10);
</script>
```

**输出:**

```
Infinity
```

在 JavaScript 中，`Number.POSITIVE_INFINITY` 代表最大正值，即正无穷大。数字的实际值。`POSITIVE_INFINITY` 与全局对象的 `Infinity` 属性的值相同。

## 语法

可以用下面的方法给变量赋值。

```javascript
var a = Number.POSITIVE_INFINITY;
```

现在，我们知道什么是 `Number.POSITIVE_INFINITY` 了，我们来看一些例子，看看对 `Number.POSITIVE_INFINITY` 进行的一些算术运算的结果。

### Example 1

当我们用任何正数乘以 `Number.POSITIVE_INFINITY` 时，结果是 `Number.POSITIVE_INFINITY`。

```javascript
<script>
var a = Number.POSITIVE_INFINITY;
document.write(a * 2);
</script>
```

**输出:**

```
Infinity
```

### Example 2

当我们用任何负数乘以 `Number.POSITIVE_INFINITY` 时，结果是负无穷大。

```javascript
<script>
var a = Number.POSITIVE_INFINITY;
document.write(a * -2);
</script>
```

**输出:**

```
Infinity
```

### Example 3

当我们用任何正数或负数除以 `Number.POSITIVE_INFINITY` 时，结果是 `0`。

```javascript
<script>
var a = Number.POSITIVE_INFINITY;
document.write(2 / a);
</script>
```

**输出:**

```
0
```

### Example 4

当我们用 `Number.POSITIVE_INFINITY` 乘以 `0` 时，结果是 `NaN`。

```javascript
<script>
var a = Number.POSITIVE_INFINITY;
document.write(a * 0);
</script>
```

**输出:**

```
NaN
```

### Example 5

当我们用 `Number.POSITIVE_INFINITY` 除以任何**负数**（`Number.NEGATIVE_INFINITY` 除外）时，结果是 `Number.NEGATIVE_INFINITY`。

```javascript
<script>
var a = Number.POSITIVE_INFINITY;
document.write(a / -2);
</script>
```

**输出:**

```
Infinity
```

### Example 6

当我们用 `Number.POSITIVE_INFINITY` 除以任何**正数**（`Number.POSITIVE_INFINITY` 除外）时，结果是 `Number.POSITIVE_INFINITY`。

```javascript
<script>
var a = Number.POSITIVE_INFINITY;
document.write(a / 2);
</script>
```

**输出:**

```
Infinity
```

### Example 7

当我们用 `Number.POSITIVE_INFINITY` 除以 `Number.NEGATIVE_INFINITY` 或 `Number.POSITIVE_INFINITY` 时，结果是 `NaN`。

```javascript
<script>
var a = Number.POSITIVE_INFINITY;
var b = Number.NEGATIVE_INFINITY;
document.write(a / b);
</script>
```

**输出:**

```
NaN
```

## 支持的浏览器

*   Google Chrome
*   Internet Explorer
*   Firefox
*   Safari
*   Opera