# JavaScript DataView.setBigUint64() 方法

> 原文：[https://www.geeksforgeeks.org/javascript-dataview-setbiguint64-method/](https://www.geeksforgeeks.org/javascript-dataview-setbiguint64-method/)

`setBigUint64()` 方法用于存储从数据视图开始的特定字节偏移量处的无符号 64 位整数（无符号长整型）值。

**语法：**

```javascript
dataview.setBigUint64(byteOffset, val [, littleEndian])
```

**参数：** 该方法接受三个参数，如下所述：

*   `byteOffset`：此参数指定从视图中读取数据的偏移量，以字节为单位。
*   `val`：此参数指定要设置为 BigUInt 的值。
*   `littleEndian`：此参数是可选的。如果为 `true`，则指示 64 位整数是以小端还是大端格式存储。如果设置为 `false` 或 `undefined`，则读取大端值。

**返回值：** 此函数返回 `undefined`。

**示例 1：** 在此示例中，偏移 0 处的值设置为 1234。

## HTML

```html
<script>
    var buffr = new ArrayBuffer(8);
    var dView = new DataView(buffr);
    dView.setBigUint64(0, 1234n);
    document.write(dView.getBigUint64(0));
</script>
```

**输出：**

```
1234
```

**示例 2：** 在此示例中，偏移 6 处的值设置为 12345678。

## HTML

```html
<script>
    // Creating an ArrayBuffer with a size in bytes
    const buffr = new ArrayBuffer(32);
    // Setting constant value
    const val = 12345678n;
    const dView = new DataView(buffr);
    dView.setBigUint64(6, val);
    document.write(dView.getBigUint64(6));
</script>
```

**输出：**

```
12345678
```