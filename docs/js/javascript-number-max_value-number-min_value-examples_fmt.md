# JavaScript Number.MAX_VALUE 与 Number.MIN_VALUE 属性详解

> 原文：[https://www.geeksforgeeks.org/javascript-number-max_value-number-min_value-examples/](https://www.geeksforgeeks.org/javascript-number-max_value-number-min_value-examples/)

下面是 `Number.MAX_VALUE` 和 `Number.MIN_VALUE` 属性的示例。

*   **示例：**

```javascript
<script>
function GFGFun() {
    document.write(Number.MAX_VALUE+"<br>");
    document.write(Number.MIN_VALUE+"<br>");
}
GFGFun();
</script>
```

*   **输出：**

```
1.7976931348623157e+308
5e-324
```

`Number.MAX_VALUE` 和 `Number.MIN_VALUE` 用于在 JavaScript 中表示最大和最小的数值。

**语法：**

```javascript
Number.MAX_VALUE
Number.MIN_VALUE
```

**返回类型：**
`Number.MAX_VALUE` 和 `Number.MIN_VALUE` 均返回一个数字。

*   `MAX_VALUE` 的值约为 1.79E+308。大于 `Number.MAX_VALUE` 的值被称为 **Infinity**。
*   `MIN_VALUE` 的值约为 5e-324。小于 `Number.MIN_VALUE` 的值被称为 **下溢值**。
*   `MAX_VALUE` 和 `MIN_VALUE` 都是数字的静态属性。因此，使用 `x.MAX_VALUE` 或 `x.MIN_VALUE`（其中 `x` 是一个数字或数字对象）将返回 `undefined`。

**示例 1：**

```
输入：Number.MAX_VALUE
输出：1.7976931348623157e+308
```

**示例 2：**

```
输入：Number.MIN_VALUE
输出：5e-324
```

**程序：**

```javascript
<script>
function GFGFun() {
    // JavaScript Code to illustrate Number.MAX_VALUE
    // & Number.MIN_VALUE
    document.write(Number.MAX_VALUE+"<br>");
    document.write(Number.MIN_VALUE+"<br>");

    // Undefined Behaviour
    var res = 1;
    res = res.MAX_VALUE;
    document.write(res);
}
GFGFun();
</script>
```

**输出：**

```
1.7976931348623157e+308
5e-324
undefined
```