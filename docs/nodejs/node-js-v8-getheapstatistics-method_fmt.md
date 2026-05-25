# Node.js V8.getHeapStatistics()方法

> 原文: [https://www.geeksforgeeks.org/node-js-v8-getheapstatistics-method/](https://www.geeksforgeeks.org/node-js-v8-getheapstatistics-method/)

`v8.getHeapStatistics()`方法是`v8`模块的内置API，用于获取从V8引擎派生的堆的统计信息。

## 语法:

```js
v8.getHeapStatistics();
```

## 参数:
该方法没有任何参数。

## 返回值:
这个方法返回一个包含V8堆统计信息的对象。返回的对象通常包含以下字段:

*   `total_heap_size`: 一个数字，表示堆的总大小。
*   `total_heap_size_executable`: 一个数字，表示可执行堆的总大小。
*   `total_physical_size`: 一个数字，表示总物理大小。
*   `total_available_size`: 一个数字，表示总可用大小。
*   `used_heap_size`: 一个数字，表示已使用的堆大小。
*   `heap_size_limit`: 一个数字，表示堆大小限制。
*   `malloced_memory`: 一个数字，表示已分配的内存。
*   `peak_malloced_memory`: 一个数字，表示峰值分配内存。
*   `does_zap_garbage`: 一个数字（布尔值），指示是否启用了`--zap_code_space`选项。
*   `number_of_native_contexts`: 一个数字，表示当前活动的原生上下文或顶级上下文的数量。通过测量此数字随时间的增加可以指示内存泄漏。
*   `number_of_disconnected_contexts`: 一个数字，表示已分离但尚未被垃圾回收的多个上下文。如果其值非零，可能表示内存泄漏。

下面的例子说明了在Node.js中使用`v8.getHeapStatistics()`方法。

### 示例 1:
**文件名: index.js**

```js
// Accessing v8 module
const v8 = require('v8');

// Calling v8.getHeapStatistics()
console.log(v8.getHeapStatistics());
```

使用以下命令运行`index.js`文件:

```bash
node index.js
```

**输出:**

```js
{ total_heap_size: 6537216,
  total_heap_size_executable: 1048576,
  total_physical_size: 6537216,
  total_available_size: 1520717240,
  used_heap_size: 4199600,
  heap_size_limit: 1526909922,
  malloced_memory: 8192,
  peak_malloced_memory: 406408,
  does_zap_garbage: 0 }
```

### 示例 2:
**文件名: index.js**

```js
// Accessing v8 module
const v8 = require('v8');

// Calling v8.getHeapStatistics()
stats = v8.getHeapStatistics();
console.log("Heap Statistics are :");

console.log("total_heap_size:"+stats['total_heap_size']);
console.log("used_heap_size:"+stats['used_heap_size']);
console.log("heap_size_limit:"+stats['heap_size_limit']);
console.log("does_zap_garbage:"+stats['does_zap_garbage']);
```

使用以下命令运行`index.js`文件:

```bash
node index.js
```

**输出:**

```js
Heap Statistics are :
total_heap_size:6537216
used_heap_size:4200640
heap_size_limit:1526909922
does_zap_garbage:0
```

**参考:** [https://nodejs.org/api/v8.html#v8_v8_getheapstatistics](https://nodejs.org/api/v8.html#v8_v8_getheapstatistics)