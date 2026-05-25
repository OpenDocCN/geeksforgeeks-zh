# Node.js EventEmitter.eventNames() 方法

> 原文: [https://www.geeksforgeeks.org/node-js-emitter-eventnames-method/](https://www.geeksforgeeks.org/node-js-emitter-eventnames-method/)

在 Node.js 中，大多数核心 API 都是围绕一个惯用的异步和事件驱动架构构建的。`EventEmitter` 类拥有由所有对象作为事件发出的实例，其中这些对象公开了一个 `eventEmitter.on()` 函数。为了处理事件，需要导入事件库 (`require('events')`)。

`emitter.eventNames()` (在 v6.0.0 中添加) 方法是事件模块的一个内置应用编程接口，用于列出 emitter 已注册侦听器的事件，并以数组形式返回。这些侦听器的类型可以是字符串或符号。

## 语法

```js
const EventEmitter = require('events');
emitter.eventNames()
```

## 参数

此功能不接受任何参数。

## 返回值

返回一个包含字符串或符号值的数组，列出发射器已注册侦听器的事件。

## 示例 1

**文件名:** `index.js`

```js
// Node.js program to demonstrate the
// emitter.eventNames() method

// Using require to access events module
const EventEmitter = require('events');

// Creating new event Emitter
const newEventEmitter = new EventEmitter();

// Creating new event akash
newEventEmitter.on('akash', () => {});

// Creating new event hadii
newEventEmitter.on('hadii', function() {});

// Error monitor function
console.log(EventEmitter.errorMonitor);

// Creating new symbol event newSymbol
const newSym = Symbol('newSymbolofGeekyWorld');
newEventEmitter.on(newSym, () => {});

// Printing event Names
console.log(newEventEmitter.eventNames());
// Prints: [ 'akash', 'hadii',
// Symbol(newSymbolofGeekyWorld) ]
```

**输出:**

> Symbol(events.errorMonitor)
>
> [ 'akash', 'hadii', Symbol(newSymbolofGeekyWorld) ]

## 示例 2

**文件名:** `index.js`

```js
// Node.js program to demonstrate the
// emitter.eventNames() method

// Using require to access events module
const EventEmitter = require('events');

// Creating new event Emitter
const newEventEmitter = new EventEmitter();

// Creating a new callback function
const someCallback = () => {
  console.log('Connected to something!');
};

// Creating new event connectSomething
newEventEmitter.on('connectSomething', someCallback);

// Creating new event alfa
newEventEmitter.prependListener('alfa', () => console.log('b'));

// Creating new event alfa, not added to eventnames array...
newEventEmitter.once('geeksforgeeks',
() => console.log('print in console...'));

// Creating new event alfa, not added to eventnames array...
newEventEmitter.prependOnceListener('geeksforgeeks',
() => console.log('geeksforgeeks'));

// Emitting geeksforgeeks event
newEventEmitter.emit('geeksforgeeks');

// Creating new symbol event newSymbolofGeekyWorld
const newSym = Symbol('newSymbolofGeekyWorld');
newEventEmitter.on(newSym, () => {});

// Printing event Names
console.log(newEventEmitter.eventNames());

// Removing connectSomething event
newEventEmitter.removeListener('connectSomething', someCallback);

// Printing event Names
console.log(newEventEmitter.eventNames());
```

使用以下命令运行 `index.js` 文件:

```bash
node index.js
```

**输出:**

> geeksforgeeks
>
> print in console...
>
> [ 'connectSomething', 'alfa', Symbol(newSymbolofGeekyWorld) ]
>
> [ 'alfa', Symbol(newSymbolofGeekyWorld) ]

## 参考

[https://nodejs.org/api/events.html#events_emitter_eventnames](https://nodejs.org/api/events.html#events_emitter_eventnames)