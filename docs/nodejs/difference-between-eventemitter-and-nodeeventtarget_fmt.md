# 事件发射器和节点事件目标之间的差异

> 原文: [https://www.geeksforgeeks.org/difference-between-eventemitter-and-nodeeventtarget/](https://www.geeksforgeeks.org/difference-between-eventemitter-and-nodeeventtarget/)

## 事件发射器

所有`EventEmitter`在添加新侦听器时发出事件`newListener`，在移除现有侦听器时发出事件`removeListener`。它由事件模块定义和公开。

要导入`EventEmitter`，请使用以下导入语句：

```js
const EventEmitter = require('events');
```

## 节点事件目标

`EventTarget`和事件对象是`EventTarget`网络应用编程接口的特定于Node.js的实现，由一些Node.js核心应用编程接口公开。

## 区别

| Event transmitter | Node event target |
| --- | --- |
| It is inherited from the `event` module of JavaScript. | Is a modified subset of the `EventEmitter` API and inherits from this API. |
| It realizes the relationship between `IS-A` and `Event` modules. | It realizes the IS-A relationship between `EventTarget` API. |
| In `EventEmitter`, we can register multiple listeners for the same event. | Each event type can register any listener once. If you try to register a listener several times, it will be ignored. |
| It imitates most from events such as `newListener`, `error`, `removeListener` and `emitted`. | 它没有模仿完整的`EventEmitter` API，如`prependListener()`、`prependOnceListener()`、`listeners()`等。 |
| The default behavior is to record `error` information and end the current execution. | For events of type `error`, it does not implement any default behavior. |
| If an error occurs in the `EventEmitter` instance, the typical operation is to issue an "error" event. | The `EventListener` object is supported as a handler for all event types. |
| All event emitters emit the event `newListener` when adding a new listener, and the event `removeListener` when removing the listener. | It is not an instance of the `EventEmitter`, and in most cases, it cannot be used instead of the event emitter. |
| **语法:** | **语法:** |
| `emitter.once(eventName, listener)` | `nodeEventTarget.once(type, listener[, options])` |

## 参考

[https://nodejs.org/api/events.html#events_nodeeventtarget_vs_eventemitter](https://nodejs.org/api/events.html#events_nodeeventtarget_vs_eventemitter)