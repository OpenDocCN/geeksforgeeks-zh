# JavaScript number . is inite()方法

> 原文:[https://www . geesforgeks . org/JavaScript-number-is inite-function/](https://www.geeksforgeeks.org/javascript-number-isfinite-function/)

下面是`number . is inite()`方法的示例。

*   **Example:**

### Javascript

```
<script type="text/javascript">
    document.write(Number.isFinite(111));         
</script>
```

*   Output:

```
true
```

JavaScript 中的`Number . is inite()`方法用于检查传递的值是否为有限的数字。

`Number . isfinite()`方法不同于`is inite()`方法，因为此方法不会强制将参数转换为数字，并且对于任何不是数字类型的值也不会返回 true。另一方面，global`isfinite()`方法首先将测试值转换为数字，然后对其进行测试。

### 语法

```
Number.isFinite(value)
```

### 参数

该方法接受单个参数`value`。它是用户想要检查有限性的数字。

### 返回值

`number . is inite()`方法返回一个布尔值，即 true 或 false。如果传递的值是数字类型，则返回真，如果等于有限的数字，则返回假。

下面是一些例子来说明 JavaScript 中的`number . is inite()`方法:

*   **Pass a negative number as parameter** : If the negative number passed to this method is finite, then this method will return true, otherwise it will return false.

### Javascript

```
<script type="text/javascript">
    document.write(Number.isFinite(-2));         
</script>
```

输出:

```
true
```

*   **Pass a positive number as the parameter** : If the positive number passed to the method is limited, the method will return true, otherwise it will return false.

### Javascript

```
<script type="text/javascript">
    document.write(Number.isFinite(2));         
</script>
```

输出:

```
true
```

*   **Pass zero as parameter** : If zero is passed to the method, the method will return true because zero is a finite number.

### Javascript

```
<script type="text/javascript">
    document.write(Number.isFinite(0));         
</script>
```

输出:

```
true
```

*   **Pass an equation as a parameter** : If the calculation result of the equation is a finite number, then this method will return true, otherwise it will return false.

### Javascript

```
<script type="text/javascript">
    document.write(Number.isFinite(7-3+2));         
</script>
```

输出:

```
true
```

*   **Pass an equation (the result is infinite) as a parameter** : If the evaluated equation does not give a finite value, then the method will return false.

### Javascript

```
<script type="text/javascript">
    document.write(Number.isFinite(0/0));         
</script>
```

输出:

```
false
```

*   **Pass a word as a parameter** : because a word is not an integer, Number.isFinite () will not convert it to Number, but will return false.

### Javascript

```
<script type="text/javascript">
    document.write(Number.isFinite("strong"));         
</script>
```

输出:

```
false
```

*   **Pass a number (string) as a parameter** : because the string is not of integer type, Number.isFinite () will not convert it into a number and will return false.

### Javascript

```
<script type="text/javascript">
    document.write(Number.isFinite("5"));         
</script>
```

输出:

```
false
```

### 支持的浏览器

*   谷歌铬合金 19
*   Internet browser 12
*   Firefox 16
*   苹果 Safari 09
*   歌剧 22