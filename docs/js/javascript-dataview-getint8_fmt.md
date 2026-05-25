# JavaScript `dataView.getInt8()` 方法

> 哎哎哎: [https://www.geeksforgeeks.org/javascript-dataview-getint8/](https://www.geeksforgeeks.org/javascript-dataview-getint8/)

下面是 `dataView.getInt8()` 方法的例子。

## 示例

### JavaScript 代码

```javascript
<script>
var buffer = new ArrayBuffer(16);
var dataview1 = new DataView(buffer, 0, 4);
dataview1.setInt8(0, 12);
document.write(dataview1.getInt8(0) + "<br>");
</script>
```

### 输出

```
12
```

## 描述

`dataView.getInt8()` 是 `DataView` 中的一种方法，用于从 `DataView` 的开始获取指定位置的字节中的 8 位整数。

## 语法

```javascript
dataview.getInt8(byteOffset)
```

## 参数

它有一个字节偏移的参数 `byteOffset`，它表示从视图开始读取数据。

## 返回值

返回 8 位有符号整数值。

## 示例 1

```javascript
Input: dataview1.setInt8(0, 123); 
       document.write(dataview1.getInt8(0)); 
Output: 123
```

## 示例 2

```javascript
Input: dataview.setInt8(3, 45); 
       document.write(dataview.getInt8(3)); 
Output: 45
```

## JavaScript 代码展示此方法的工作原理

### 代码 #1

```javascript
<script>
// Create buffer
var buffer = new ArrayBuffer(16);

// Create one view
var dataview1 = new DataView(buffer, 0, 4);

// put the data at slot 0
dataview1.setInt8(0, 123);
document.write(dataview1.getInt8(0) + "<br>");

// create another view
var dataview2 = new DataView(buffer, 1, 2);

// put data at slot 1
dataview2.setInt8(1, 45);
document.write(dataview2.getInt8(1));
</script>
```

### 输出

```
123
45
```

### 代码 #2

```javascript
<script>
// Create buffer
var buffer = new ArrayBuffer(16);
var dataview = new DataView(buffer, 0, 10);

// put data at slots
dataview.setInt8(0, 12);
dataview.setInt8(1, 23);
dataview.setInt8(2, 34);
dataview.setInt8(3, 45);
dataview.setInt8(4, 67);
dataview.setInt8(5, 78);
dataview.setInt8(6, 89);
dataview.setInt8(7, 90);
dataview.setInt8(8, 123);

// print the value using getInt8 method that
// prints the first 8 int
document.write(dataview.getInt8(0) + "<br>");
document.write(dataview.getInt8(1) + "<br>");
document.write(dataview.getInt8(2) + "<br>");
document.write(dataview.getInt8(3) + "<br>");
document.write(dataview.getInt8(4) + "<br>");
document.write(dataview.getInt8(5) + "<br>");
document.write(dataview.getInt8(6) + "<br>");
document.write(dataview.getInt8(7) + "<br>");
document.write(dataview.getInt8(8));
</script>
```

### 输出

```
12
23
34
45
67
78
89
90
123
```

## 支持的浏览器

*   谷歌 Chrome 9 及以上版本
*   边缘 12 及以上
*   Firefox 15 及以上版本
*   Internet Explorer 10 及以上版本
*   Opera 12.1 及以上
*   Safari 5.1 及以上版本