# Node.js os.cpus() 方法

> 原文: [https://www.geeksforgeeks.org/node-js-os-cpus-method/](https://www.geeksforgeeks.org/node-js-os-cpus-method/)

`os.cpus()` 方法是 `os` 模块的内置应用编程接口，用于获取计算机每个逻辑 CPU 内核的信息。

## 语法

```js
os.cpus()
```

## 参数

此方法不接受任何参数。

## 返回值

这个方法返回一个包含每个逻辑 CPU 核心信息的对象。每个返回的对象将包含以下属性：

*   `model`: 一个字符串，指定 CPU 内核型号。
*   `speed`: 一个数字，指定 CPU 核心速度（以兆赫兹为单位）。
*   `time`: 包含以下属性的对象：
    *   `user`: 一个数字，指定 CPU 在用户模式下花费的时间（以毫秒为单位）。
    *   `nice`: 一个数字，指定 CPU 在 nice 模式下花费的时间（以毫秒为单位）。
    *   `sys`: 一个数字，指定 CPU 在系统模式下花费的时间（以毫秒为单位）。
    *   `idle`: 一个数字，指定 CPU 在空闲模式下花费的时间（以毫秒为单位）。
    *   `irq`: 一个数字，指定 CPU 在 IRQ 模式下花费的时间（以毫秒为单位）。

## 注意

`nice` 值仅用于 POSIX。在 Windows 操作系统上，所有处理器的 `nice` 值始终为 0。

下面的例子说明了 `os.cpus()` 方法在 Node.js 中的使用：

### 例 1

```js
// Node.js program to demonstrate the
// os.cpus() method

// Allocating os module
const os = require('os');

// Printing os.cpus() values
console.log(os.cpus());
```

**输出：**

```js
[ { model: 'Intel(R) Core(TM) i5-7200U CPU @ 2.50GHz',
    speed: 2712,
    times:
     { user: 900000, nice: 0, sys: 940265, idle: 11928546, irq: 147046 } },
  { model: 'Intel(R) Core(TM) i5-7200U CPU @ 2.50GHz',
    speed: 2712,
    times:
     { user: 860875, nice: 0, sys: 507093, idle: 12400500, irq: 27062 } },
  { model: 'Intel(R) Core(TM) i5-7200U CPU @ 2.50GHz',
    speed: 2712,
    times:
     { user: 1273421, nice: 0, sys: 618765, idle: 11876281, irq: 13125 } },
  { model: 'Intel(R) Core(TM) i5-7200U CPU @ 2.50GHz',
    speed: 2712,
    times:
     { user: 943921, nice: 0, sys: 460109, idle: 12364453, irq: 12437 } } ]
```

### 例 2

```js
// Node.js program to demonstrate the
// os.cpus() method

// Allocating os module
const os = require('os');

// Printing os.cpus()
var cpu_s=os.cpus();
var no_of_logical_core=0;
cpu_s.forEach(element => {
    no_of_logical_core++;
    console.log("Logical core "
            + no_of_logical_core + " :");
    console.log(element);
});

console.log("total number of logical core is "
        + no_of_logical_core);
```

**输出：**

```js
Logical core 1 :
{ model: 'Intel(R) Core(TM) i5-7200U CPU @ 2.50GHz',
  speed: 2712,
  times:
   { user: 856437, nice: 0, sys: 866203, idle: 11070046, irq: 133562 } }
Logical core 2 :
{ model: 'Intel(R) Core(TM) i5-7200U CPU @ 2.50GHz',
  speed: 2712,
  times:
   { user: 805296, nice: 0, sys: 462656, idle: 11524406, irq: 23218 } }
Logical core 3 :
{ model: 'Intel(R) Core(TM) i5-7200U CPU @ 2.50GHz',
  speed: 2712,
  times:
   { user: 1225062, nice: 0, sys: 566421, idle: 11000875, irq: 12203 } }
Logical core 4 :
{ model: 'Intel(R) Core(TM) i5-7200U CPU @ 2.50GHz',
  speed: 2712,
  times:
   { user: 900234, nice: 0, sys: 420000, idle: 11472125, irq: 11781 } }
total number of logical core is 4
```

## 注意

以上程序使用 `node index.js` 命令编译运行。

## 参考

[https://nodejs.org/api/os.html#os_os_cpus](https://nodejs.org/api/os.html#os_os_cpus)