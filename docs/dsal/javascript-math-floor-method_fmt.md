# JavaScript Math.floor() 方法

> 原文: [https://www.geeksforgeeks.org/javascript-math-floor-method/](https://www.geeksforgeeks.org/javascript-math-floor-method/)

下面是 `Math.floor()` 方法的例子。

### 示例

```javascript
<script type="text/javascript">
    document.write("Result : " + Math.floor(.89));
</script>
```

**输出:**

```
Result : 0
```

`Math.floor()` 方法用于将作为参数传递的数字舍入到向下舍入方向上最接近的整数，即舍入到较小的值。

## 语法

```
Math.floor(value)
```

## 参数

该方法接受单个参数：

*   `value`: 是要进行数学测试的值。

## 返回值

`Math.floor()` 方法返回大于或等于给定数字的最小整数。

以下示例说明了 JavaScript 中的 `Math.floor()` 方法：

### 示例 1

```
Input : Math.floor(.89)
Output: 0
```

### 示例 2

```
Input : Math.floor(-89.02)
Output : -90
```

### 示例 3

```
Input : Math.floor(0)
Output : 0
```

上述方法的更多代码如下：

### 程序 1

当负数作为参数传递时。

```javascript
<script type="text/javascript">
    document.write("Result : " + Math.floor(-89.02));
</script>
```

**输出:**

```
Result : -90
```

### 程序 2

当零作为参数传递时。

```javascript
<script type="text/javascript">
    document.write("Result : " + Math.floor(0));
</script>
```

**输出:**

```
Result : 0
```

## 支持的浏览器

*   Google Chrome
*   Internet Explorer
*   Firefox
*   Opera
*   Safari