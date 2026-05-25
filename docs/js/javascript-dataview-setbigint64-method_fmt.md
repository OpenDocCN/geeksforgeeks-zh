# DataView.setBigInt64() 方法

> 原文: [https://www.geeksforgeeks.org/javascript-dataview-setbigint64-method/](https://www.geeksforgeeks.org/javascript-dataview-setbigint64-method/)

``setBigInt64()`` 方法用于存储从数据视图开始的特定字节偏移量处的有符号 64 位整数（长整型）值。

## 语法

```
dataview.setBigInt64(byteOffset, val [, littleEndian])
```

## 参数

*   `byteOffset`: 此参数指定从视图中读取数据的偏移量，以字节为单位。
*   `val`: 此参数指定要设置为 BigInt 的值。
*   `littleEndian`: 此参数可选。如果为 true，则表示 64 位整数是以小端还是大端格式存储。如果设置为 false 或 undefined，则按大端格式读取值。

## 返回值

此函数不返回任何值。

## 示例 1

在此示例中，偏移 0 处的值设置为 7。

```javascript
<script>
    var buffr = new ArrayBuffer(8);
    var dView = new DataView(buffr);
    dView.setBigInt64(0, 7n);
    document.write(dView.getBigInt64(0));
</script>
```

**输出:**

```

```

## 示例 2

在此示例中，偏移 4 处的值设置为 789。

```javascript
<script>
    // create an ArrayBuffer with a size in bytes
    const buffr = new ArrayBuffer(16);
    // constant value to set
    const val = 789n;
    const dView = new DataView(buffr);
    dView.setBigInt64(4, val);
    document.write(dView.getBigInt64(4));
</script>
```

**输出:**

```

```