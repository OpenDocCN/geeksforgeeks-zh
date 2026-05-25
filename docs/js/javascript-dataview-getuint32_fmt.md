# DataView.getUint32()方法

> 哎哎哎:# t0]https://www . geeksforgeeks . org/JavaScript-dataview-getuint 32/

下面是`dataView.getUint32()`方法的例子。

## 示例

### JavaScript 代码

```javascript
<script>
   var buffer = new ArrayBuffer(20);

   var dataview1 = new DataView(buffer, 0, 10);

   dataview1.getUint32(1, 12);
   document.write(dataview1.getUint32(1));
</script>
```

**输出:**

```


```

## 描述

`dataView.getUint32()`是`DataView`中的一个内置函数，用于在指定位置，即从`DataView`开始的字节偏移量处获取一个无符号的 32 位整数。

**语法:**

```javascript
dataView.getUint32(byteOffset)
```

**参数:**它有一个字节偏移的参数`byteOffset`，即从视图开始读取数据。
**返回值:**返回一个无符号的 32 位整数。

## 示例 1

```javascript
Input: dataview1.getUint32(1, 56);
Output: 56
```

## 示例 2

```javascript
Input: dataview1.getUint32(1, Math.PI);
Output: 3
```

## 代码演示

### 代码#1

```javascript
<script>
   // Creating buffer with size in byte
   var buffer = new ArrayBuffer(20);

   // Creating a view
   var dataview1 = new DataView(buffer, 0, 10);

   // put the data 56 at slot 1
   dataview1.setUint32(1, 56);
   document.write(dataview1.getUint32(1) + "<br>");
</script>
```

**输出:**

```


```

### 代码#2

该功能将 PI 的浮点值从 3.14 转换为 3。

```javascript
<script>
   // Creating buffer with size in byte
   var buffer = new ArrayBuffer(20);

   // Creating a view with slot from o to 10
   var dataview1 = new DataView(buffer, 0, 10);

   // put the value of PI at slot 1
   dataview1.setUint32(1, Math.PI);
   document.write(dataview1.getUint32(1) + "<br>");
</script>
```

**输出:**

```


```

### 代码#3

当没有数据要存储时，则返回零(0)。

```javascript
<script>
   // Creating buffer with size in byte
   var buffer = new ArrayBuffer(20);

   // Creating a view
   var dataview1 = new DataView(buffer, 0, 10);

   // putting no data at slot 1
   dataview1.setUint32(1);
   document.write(dataview1.getUint32(1) + "<br>");
</script>
```

**输出:**

```


```

## 支持的浏览器

*   谷歌 Chrome 9 及以上版本
*   边缘 12 及以上
*   Firefox 15 及以上版本
*   Internet Explorer 10 及以上版本
*   Opera 12.1 及以上
*   Safari 5.1 及以上版本