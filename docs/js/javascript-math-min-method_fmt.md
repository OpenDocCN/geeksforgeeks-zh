# JavaScript Math.min() 方法

> 原文：[https://www.geeksforgeeks.org/javascript-math-min-method/](https://www.geeksforgeeks.org/javascript-math-min-method/)

下面是 `Math.min()` 方法的例子。

## 示例

```javascript
<script type="text/javascript">
    document.write("When positive numbers are passed" +
                   " as parameters: " + Math.min(10, 32, 2));
</script>
```

**输出：**

```
When positive numbers are passed as parameters: 2
```

`Math.min()` 方法用于返回传递给该方法的数字中的最小值。如果任何参数不是数字且无法转换为数字，则 `Math.min()` 方法返回 `NaN`。`min()` 是 `Math` 的静态方法，因此，它总是作为 `Math.min()` 调用，而不是作为已创建的 `Math` 对象的方法。

## 语法

```
Math.min(value1, value2, ...)
```

## 参数

该方法接受可使用 n 次的单个参数，如下所述：

*   **值：** 传递给 `Math.min()` 方法以求最小值的数字。

## 返回值

`Math.min()` 方法返回给定数字中的最小值。

## 更多示例

以下示例说明了 JavaScript 中的 `Math.min()` 方法：

**示例 1：**

```
输入：Math.min(10, 32, 2)
输出：2
```

**示例 2：**

```
输入：Math.min(-10, -32, -1)
输出：-32
```

**示例 3：**

```
输入：Math.min()
输出：Infinity
```

**示例 4：**

```
输入：Math.min(10, 2, NaN)
输出：NaN
```

## 完整代码示例

**程序 1：** 当负数作为参数传递时。

```javascript
<script type="text/javascript">
    document.write("Result : " + Math.min(-10, -32, -1));
</script>
```

**输出：**

```
Result : -32
```

**程序 2：** 当没有传递参数时。

```javascript
<script type="text/javascript">
    document.write("Result : " + Math.min());
</script>
```

**输出：**

```
Result : Infinity
```

**程序 3：** 当 `NaN` 作为参数传递时。

```javascript
<script type="text/javascript">
    document.write("Result : " + Math.min(10, 2, NaN));
</script>
```

**输出：**

```
Result : NaN
```

## 支持的浏览器

*   Google Chrome
*   Internet Explorer
*   Firefox
*   Opera
*   Safari