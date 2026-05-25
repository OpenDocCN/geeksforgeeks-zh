# JavaScript BigInt.asUintN() 方法

> 原文：[https://www.geeksforgeeks.org/javascript-bigint-asuintn-method/](https://www.geeksforgeeks.org/javascript-bigint-asuintn-method/)

`BigInt.asUintN()` 方法是 JavaScript 中的内置方法，用于将 BigInt 值包装为 0 到 2<sup>width</sup>-1 之间的无符号整数。

**语法：**

```javascript
BigInt.asUintN(width, bigint);
```

**参数：** 该方法接受两个参数，如下所述：

*   `width`：此参数保存整数大小的可用位数。
*   `bigint`：此参数保存要箝位的整数，以适合所提供的位。

**返回值：** 该方法以无符号整数形式返回 bigint 模 2<sup>width</sup> 的值。

以下示例说明了 JavaScript 中的 `BigInt.asUintN()` 方法：

**示例 1：**

```javascript
<script>
let maxlimit = 2n ** (64n - 1n) - 1n;

function GFG(num) {
  (num > maxlimit) ?
    console.log("Number exceed the limit "
           + "of signed 64-bit integer!"):
    console.log(BigInt.asUintN(64, num));
}

GFG(2n ** 16n);
GFG(2n ** 32n);
GFG(2n ** 64n);
</script>
```

**输出：**

```
65536n
4294967296n
"Number exceed the limit of signed 64-bit integer!"
```

**示例 2：**

```javascript
<script>
const max = 2n ** (64n - 1n) - 1n;

console.log(BigInt.asUintN(64, max));
console.log(BigInt.asUintN(64, max + 1n));
console.log(BigInt.asUintN(32, max));
</script>
```

**输出：**

```
9223372036854775807n
9223372036854775808n
4294967295n
```

**支持的浏览器：** `BigInt.asUintN()` 方法支持的浏览器如下：

*   Google Chrome 67 及以上
*   Edge 79 及以上
*   Firefox 68 及以上版本
*   Opera 54 及以上
*   Safari 14 及以上