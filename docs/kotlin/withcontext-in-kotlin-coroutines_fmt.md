# 科特林 coroutines 中的 withContext

> 原文: [https://www.geeksforgeeks.org/withcontext-in-kotlin-coroutines/](https://www.geeksforgeeks.org/withcontext-in-kotlin-coroutines/)

## 先决条件

*   [The Coroutines of Kotlin on Android](https://www.geeksforgeeks.org/kotlin-coroutines-on-android/)
*   [Launch vs Async in Kotlin Coroutines](https://www.geeksforgeeks.org/launch-vs-async-in-kotlin-coroutines/)

众所周知，`async`和`launch`是启动`coroutine`的两种方式。由于已知`async`是用来取回结果的，所以应该只在我们需要并行执行的时候使用，而`launch`是在我们不想取回结果的时候使用，用于数据更新等操作。正如我们所知，`async`是到目前为止启动协程并返回结果的唯一方法，但是当我们不想进行并行网络调用时，`async`的问题就出现了。众所周知，当使用`async`时，需要使用`await()`函数，这将导致阻塞主线程，但这里出现了`withContext`的概念，它消除了阻塞主线程的问题。

`withContext`只不过是写`async`的另一种方式，在这种方式中，不必写`await()`。当使用`withContext`时，它以串行方式而不是并行方式运行任务。因此，人们应该记住，当我们在后台有一个单一的任务，并且想要获得该任务的结果时，我们应该使用`withContext`。让我们举一个例子来说明`withContext`的工作原理:

## Kotlin 代码示例

```kt
// two kotlin suspend functions
// Suppose we have two tasks like below

private suspend fun doTaskOne(): String
{
  delay(2000)
  return "One"
}

private suspend fun doTaskTwo(): String
{
  delay(2000)
  return "Two"
}
```