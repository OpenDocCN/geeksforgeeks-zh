# PHP 预定义的类和接口

> Original: [https://www.geeksforgeeks.org/php-predefined-classes-and-interfaces/](https://www.geeksforgeeks.org/php-predefined-classes-and-interfaces/)

有[类](https://www.geeksforgeeks.org/php-classes/)和[接口](https://www.geeksforgeeks.org/php-interface/)可以是用户定义的，也可以是 PHP 语言预定义的。

PHP 中有 9 个预定义的类和接口：

*   `Traversable`
*   `Iterator`
*   `IteratorAggregate`
*   `Throwable`
*   `ArrayAccess`
*   `Serializable`
*   `Closure`
*   `Generator`

## `Traversable`

`Traversable` 接口中没有方法，仅充当其他预定义的 `Traversable` 类的基础。 通过使用 `foreach` 构造和此接口，可以很容易地检测到类是否可遍历。

## `Iterator`

这是一个预定义的接口，用于能够内部迭代自身的对象或外部迭代器。 此接口扩展了 `Traversable` 接口。 该接口的五个方法分别是：

| Method name | Parameters | Return value | Description |
| --- | --- | --- | --- |
| `current()` | `void` | `mixed` | Returns the present value. |
| `key()` | `void` | `scalar` | Returns the key of the current value. |
| `next()` | `void` | `void` | Move on to the next element. |
| `rewind()` | `void` | `void` | 将文件指针的位置设置为文件的开头。 |
| `valid()` | `void` | `bool` | Check to see if the array contains more entries. |

## `IteratorAggregate`

此接口是 `Traversable` 接口的扩展，只有一个方法。

| Method name | Parameters | Return type | Description |
| --- | --- | --- | --- |
| `getIterator()` | `void` | `Traversable` | This function is used to retrieve iterators (external). |

## `Throwable`

此功能在 PHP 版本 7 中可用。所有通过 `throw` 语句抛出的对象都有一个接口，该接口充当称为 `Throwable` 的基接口。 `Exception` 和 `Error` 类使用此接口。

| Method name | Number of parameters | Parameter name | Return type | Description |
| --- | --- | --- | --- | --- |
| `getMessage()` | 0 | `void` | `string` | 获取消息 |
| `getPrevious()` | 0 | `void` | `Throwable` | The previous exception was returned. |
| `getCode()` | 0 | `void` | `mixed` | The generated exception code. |
| `getFile()` | 0 | `void` | `string` | Returns the file where the exception occurred. |
| `getLine()` | 0 | `void` | `int` | Returns the line number where the exception occurred. |
| `getTrace()` | 0 | `void` | `array` | Return to the stack trace. |
| `getTraceAsString()` | 0 | `void` | `string` | The stack trace is returned as a string. |
| `__toString()` | 0 | `void` | `string` | The generated exception is returned as a string. |

## `ArrayAccess`

此接口允许将对象作为数组进行访问。 它有 4 个方法：

| Method name | Parameters | Return | Description |
| --- | --- | --- | --- |
| `offsetExists()` | `offset` (`mixed`) | `bool` | Check to see if there is an offset. |
| `offsetGet()` | `offset` (`mixed`) | `mixed` | The offset is retrieved by this method. |
| `offsetSet()` | `offset` (`mixed`), `value` (`mixed`) | `void` | The above offset is assigned some values. |
| `offsetUnset()` | `offset` (`mixed`) | `void` | The offset value is not set. |

## `Serializable`

这个类允许以定制的方式进行序列化。 如果需要序列化实例，则调用 `serialize()`方法。 如果它是在某个方法内部的代码中编写的，则不会对程序产生任何更改或副作用。 该接口有两个方法：

| Method name | Parameters | Return | Description |
| --- | --- | --- | --- |
| `serialize()` | `void` | `string` | Object to a string. |
| `unserialize()` | `serialized` (`string`) | `void` | Objects that are converted to strings are converted back to objects. |

## `Closure`

PHP 中有一些称为匿名函数的函数没有名称。 回调参数被赋值为匿名函数。 有 5 种方法：

| Method name | Parameters | Return | Description |
| --- | --- | --- | --- |
| `__construct()` | `void` | `void` | Constructor does not allow instantiation. |
| `bind()` | `newThis` (`object`), `newScope` (`object`) | `Closure` | Closures can be copied by the class scope and the specific binding objects mentioned. |
| `bindTo()` | `newThis` (`object`), `newScope` (`object`) | `Closure` | Closures can be copied by class scope and newly bound objects. |
| `call()` | `newThis` (`object`) | `mixed` | Bind and invoke the closure. |
| `fromCallable()` | `callable` (`callable`) | `Closure` | Callable objects are converted to closures. |

## `Generator`

此接口是 `Iterator` 的扩展，有 9 个方法：

| Method name | Parameters | Return | Description |
| --- | --- | --- | --- |
| `current()` | `void` | `mixed` | Returns the current value. |
| `getReturn()` | `void` | `mixed` | Function returns the value of the generator. |
| `key()` | `void` | `mixed` | Returns the resulting key. |
| `next()` | `void` | `void` | Moves the generator point to the next value. |
| `rewind()` | `void` | `void` | Rewinds the generator to the first value. |
| `send()` | `value` (`mixed`) | `mixed` | If the value is sent to the generator. |
| `throw()` | `exception` (`Throwable`) | `mixed` | If the exception is thrown into the generator. |
| `valid()` | `void` | `bool` | Verify that the iterator is off. |
| `__wakeup()` | `void` | `void` | The callback is serialized. |