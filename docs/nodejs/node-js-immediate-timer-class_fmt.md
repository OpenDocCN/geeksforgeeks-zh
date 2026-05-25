# Node.js 即时定时器类

> 原文: [https://www.geeksforgeeks.org/node-js-immediate-timer-class/](https://www.geeksforgeeks.org/node-js-immediate-timer-class/)

计时器模块用于调度将在未来某个时间段调用的功能。它是一个全局 API，所以不需要导入 (`require("timers")`) 来使用它。

`Immediate` 类有一个对象 (`setImmediate()`) 是内部为预定动作创建的，可以传递 (`clearImmediate()`) 来取消那些预定动作。当调度立即 (`setImmediate()`) 时，默认情况下，Node.js 的事件循环将继续运行，直到调用 `clearImmediate()` 为止。`setImmediate()` 方法返回用于控制该默认行为的 `Immediate` 对象，导出 `Immediate.ref()` 和 `Immediate.unref()` 函数。

## 三个直接类对象定义如下

### 1. `Immediate.hasRef()`
(在 v11.0.0 中添加) 此 `Immediate` 对象使事件循环保持活动状态，直到返回的“True”(如果返回的“false”)打破事件循环。

**语法:**

```js
immediate.hasRef()
```

**返回值** < `布尔` >: 如果返回“真”，该立即对象将保持事件循环活动。

### 2. `Immediate.ref()`
(在 v9.7.0 中添加) 当 `Immediate` 处于活动状态并且 (`Immediate.ref()`) 被调用时，它会请求 Node.js 事件循环没有退出这么长时间。无论如何，多次调用此方法没有任何效果。

**语法:**

```js
immediate.ref()
```

**返回值** < `Immediate` >: 返回 `Immediate` 引用。

### 3. `Immediate.unref()`
(在 v9.7.0 中添加) 当 `Immediate` 处于活动状态时，它不要求 Node.js 事件循环保持活动状态。如果任何其他活动保持事件循环运行，则在进程退出后调用立即对象的回调。反正多次调用这个方法也没有任何效果。

**语法:**

```js
immediate.unref()
```

**返回值** < `Immediate` >: 返回 `Immediate` 引用。

**示例: 文件名: `index.js`**

## java 描述语言

```js
// Node.js program to demonstrate the
// Immediate Class methods

// Setting Immediate by setImmediate Method
var Immediate = setImmediate(function alfa() {
    console.log("0.>",12);
});

// Printing Immediate.hasRef method
console.log("1.>",Immediate.hasRef());
// Returns true

// Printing Immediate.ref before unref
console.log("2.>",Immediate.ref());
// Returns timer reference

// Printing Immediate.unref method
console.log("3.>",Immediate.unref());
// Returns Immediate reference and
// sets hasRef to false

// Printing Immediate.hasRef before unref
console.log("4.>",Immediate.hasRef());
// Returns false

// Clears setInterval Immediate
clearImmediate(Immediate);

// Prints after clearing Immediate
console.log("5.>",2);
```

使用以下命令运行 `index.js` 文件:

```js
node index.js
```

**输出:**

> 1.> true
>
> 2.> Immediate {
>
> _idleNext: null, ……, [Symbol(triggerId)]: 1
>
> }
>
> 3.> Immediate {
>
> _idleNext: null, ……, [Symbol(triggerId)]: 1
>
> }
>
> 4.> false
>
> 5.> 2

**参考:** [https://nodejs.org/api/timers.html#timers_class_immediate](https://nodejs.org/api/timers.html#timers_class_immediate)