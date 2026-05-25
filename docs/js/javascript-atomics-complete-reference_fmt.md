# JavaScript 原子完全参考

> 原文: [https://www.geeksforgeeks.org/javascript-atomics-complete-reference/](https://www.geeksforgeeks.org/javascript-atomics-complete-reference/)

`Atomics` 是 JavaScript 中的一个对象，它提供了作为静态方法执行的原子操作。就像 JavaScript 中的 `Math` 对象一样，`Atomics` 的所有属性和方法也是静态的。`Atomics` 与 `SharedArrayBuffer`（通用固定长度二进制数据缓冲区）对象一起使用。`Atomics` 不是像其他全局对象那样的构造函数。`Atomics` 不能与 `new` 运算符一起使用，也不能作为函数调用。

JavaScript 原子的完整列表如下:

## 静态方法

*   [`Atomics.add()` 方法](https://www.geeksforgeeks.org/atomics-add-javascript/)
*   [`Atomics.and()` 方法](https://www.geeksforgeeks.org/atomics-and-in-javascript-2/)
*   [`Atomics.compareExchange()` 方法](https://www.geeksforgeeks.org/atomics-compareexchange-javascript/)
*   [`Atomics.exchange()` 方法](https://www.geeksforgeeks.org/atomics-exchange-javascript/)
*   [`Atomics.isLockFree()` 方法](https://www.geeksforgeeks.org/atomics-islockfree-javascript/)