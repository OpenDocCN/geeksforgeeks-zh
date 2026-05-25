# JavaScript 中的原子

> 原文: [https://www.geeksforgeeks.org/atomics-in-javascript/](https://www.geeksforgeeks.org/atomics-in-javascript/)

**Atomics:** `Atomics` 是一个 JavaScript 对象，它赋予原子任务以静态策略进行。与数学对象的策略一样，`Atomics` 的技术和属性也是静态的。`Atomics` 与 `SharedArrayBuffer` 对象一起使用。原子活动是在原子模块中引入的。与世界范围内的其他文章相比，`Atomics` 不是一个构造器。原子不能被另一个管理员使用，也不能作为一种能力被召唤。

**原子操作:** 原子操作不是连续的。共享内存时，多线程可以在内存中读写数据。如果任何数据发生变化，就会出现数据丢失。原子操作确保数据按照预测值写入和准确读取。在当前操作完成和原子操作开始之前，无法更改现有信息。

## 方法

*   [`Atomics.add()`](https://www.geeksforgeeks.org/atomics-add-javascript/): 将提供的值添加到指定数组索引中的当前值。返回旧的索引值。
*   [`Atomics.and()`](https://www.geeksforgeeks.org/atomics-and-in-javascript/): 按位计算指定数组索引处的值与提供值的 AND。返回该索引的旧值。
*   [`Atomics.exchange()`](https://www.geeksforgeeks.org/atomics-exchange-javascript/): 在指定的数组索引处设置一个值。返回旧值。
*   [`Atomics.compareExchange()`](https://www.geeksforgeeks.org/atomics-compareexchange-javascript/): 如果值相同，则设置指定数组索引中的值。返回旧值。
*   [`Atomics.isLockFree(size)`](https://www.geeksforgeeks.org/atomics-islockfree-javascript/): 原始优化，确定是使用锁还是原子操作。如果在给定元素大小的数组中执行硬件原子操作（与锁相反），则返回 `true`。
*   [`Atomics.load()`](https://www.geeksforgeeks.org/atomics-load-javascript/): 返回指定数组索引处的值。
*   `Atomics.or()`: 按位计算指定数组索引处给定值的 OR。返回旧的索引值。
*   [`Atomics.notify()`](https://www.geeksforgeeks.org/javascript-atomics-notify-method/): 通知等待指定数组索引的代理。返回通知的代理数。
*   [`Atomics.sub()`](https://www.geeksforgeeks.org/atomics-sub-javascript/): 从指定数组索引处的值中减去一个值。返回旧的索引值。
*   [`Atomics.store()`](https://www.geeksforgeeks.org/atomics-store-javascript/): 在指定的数组索引上存储一个值。返回该值。
*   [`Atomics.wait()`](https://www.geeksforgeeks.org/javascript-atomics-wait-method/): 验证指定的数组索引仍然有该值，并等待或休眠直到被唤醒或超时。返回 `"ok"`、`"not-equal"` 或 `"timed-out"`。如果调用代理无法等待，它会抛出一个错误异常。
*   [`Atomics.xor()`](https://www.geeksforgeeks.org/atomics-xor-javascript/): 计算给定数组索引上给定值的按位异或。返回旧的索引值。

## 例 1

```javascript
var buffer = new SharedArrayBuffer(50); // 创建一个 SharedArrayBuffer
var a = new Uint8Array(buffer);
// 将数组零索引位置的元素初始化为 9
a[0] = 9;
console.log(Atomics.load(a, 0)); // 显示 Atomics.store() 方法的返回值
console.log(Atomics.store(a, 0, 3)); // 显示更新后的 SharedArrayBuffer
console.log(Atomics.load(a, 0));
```

**输出:**

```
9
3
3
```

## 例 2

```javascript
const buffer = new SharedArrayBuffer(2048);
const ta = new Uint8Array(buffer);

ta[0]; // 0
ta[0] = 5; // 5

Atomics.add(ta, 0, 12);   // 5
Atomics.load(ta, 0);      // 17

Atomics.and(ta, 0, 1); // 17
Atomics.load(ta, 0); // 1

Atomics.exchange(ta, 0, 12); // 1
Atomics.load(ta, 0); // 12

Atomics.compareExchange(ta, 0, 5, 12); // 1
Atomics.load(ta, 0); // 1

Atomics.isLockFree(1); // true
Atomics.isLockFree(2); // true

Atomics.or(ta, 0, 1); // 12
Atomics.load(ta, 0);  // 13

Atomics.store(ta, 0, 12); // 12
Atomics.sub(ta, 0, 2); // 12
Atomics.load(ta, 0); // 10

Atomics.xor(ta, 0, 1); // 10
Atomics.load(ta, 0); // 11
```

**输出:**

```
5
true
true
10
```