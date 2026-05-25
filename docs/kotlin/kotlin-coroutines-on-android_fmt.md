# 安卓上的 Kotlin Coroutines

> 哎哎哎: https://www.geeksforgeeks.org/kotlin-coroutines-on-Android/

异步编程非常重要，现在它是现代应用程序的一个常见部分。它增加了应用程序可以并行执行的工作量。这允许在后台运行远离 UI Thread 的繁重任务，最终为应用程序的用户带来流畅且更好的体验。

## Kotlin 的 Coroutines

[Kotlin](https://www.geeksforgeeks.org/kotlin-programming-language/) 团队将协程定义为“**轻量级线程**”。它们是实际线程可以执行的任务。Coroutines 在 1.3 版本中被添加到 Kotlin 中，并且是基于其他语言的既定概念。Kotlin coroutines 引入了一种新的并发风格，可以在 Android 上使用来简化异步代码。

> **官方文件称，coroutines 是轻量级线程。通过轻量级，意味着创建协同程序不会分配新的线程。相反，它们使用预定义的线程池和智能调度来决定下一步执行哪个任务以及以后执行哪个任务**。

协程基本上有两种类型:

*   无栈（Stackless）
*   有栈（Stackful）

**Kotlin 实现无栈的 coroutines，** 表示 coroutines 没有自己的栈，所以不映射在原生线程上。

## 为什么我们需要 Coroutines？

正如我们所知，如今安卓开发者手里有很多异步工具。这些包括 RxJava、AsyncTask、Job、Thread。那么为什么需要学习新的东西呢？

*   When using Rx, it takes a lot of effort to get enough to use it safely. On the other hand, asynchronous tasks and threads can easily introduce leakage and memory overhead. Even if these tools are used after so many shortcomings, the code will suffer from [callback](https://www.geeksforgeeks.org/callbacks-in/c/) , which will introduce a lot of extra code. Not only that, the code also becomes unreadable, because it has many callbacks, which will eventually slow down or hang up the device, resulting in poor user experience.
*   Android is a single-threaded platform. By default, everything runs on the main thread. In Android, almost every application needs to perform some non-UI operations, such as (Network call, I/O operation), so when the concept of coroutines is not introduced, what the programmer does is to dedicate this task to different threads, and each thread performs the task assigned to it. When the task is completed, they return the result to the UI thread to update the required changes. Although a detailed process is given in android about how to use threads to perform this task effectively with best practices, this process includes many callbacks for transferring results between threads, which will eventually introduce a lot of code into our application and increase the waiting time for returning results.
*   On Android, each application has a main thread (which handles all UI operations, such as drawing views and other user interactions). If too much work happens on this main thread, such as network calls (such as getting web pages), the application will hang up or slow down, resulting in poor user experience.

## Kotlin Coroutines 特征

Coroutines 是安卓上**异步编程的推荐解决方案。** 协程的一些突出特征如下。

*   **轻量级（Lightweight）** : 因为有挂起（suspension）支持，一个线程可以运行多个协程而不会阻塞运行协程的线程。挂起释放内存而不是阻塞，并支持多个并发操作。
*   **内置取消支持（Built-in cancellation support）** : 取消操作由运行的协程层级自动生成。
*   **更少的内存泄漏（Less memory leakage）** : 它使用结构化并发（structured concurrency）来运行一系列操作。
*   **Jetpack 集成（Jetpack integration）** : 许多 Jetpack 库包含提供完整协程支持的扩展。一些库还提供自己的协程作用域（coroutine scope），可用于结构化并发。

## Kotlin Coroutines vs Threads

*   从一个线程获取数据并将其传递给另一个线程需要很多时间。它还引入了大量回调，导致代码可读性降低。另一方面，协同程序消除了回调。
*   创建和停止线程是一项昂贵的工作，因为它涉及创建自己的栈。而与它提供的性能相比，创建协同程序非常便宜。协同程序没有自己的栈。
*   线程是阻塞的，而协同程序是可挂起的。阻塞意味着当一个线程休眠一段时间后，整个线程都会被阻塞，它不能执行任何其他操作，而由于协同程序是可挂起的，所以当它们延迟几秒钟时，它们可以执行任何其他工作。
*   与线程相比，Coroutines 提供了非常高的并发级别，因为多线程涉及阻塞和上下文切换。与 coroutine 相比，线程的上下文切换更慢，因为线程的上下文只能在 1 个线程的工作结束时切换，但是使用 coroutine，它们可以随时更改上下文，因为它们是可挂起的。
*   协程很轻，速度超快。协同程序比线程快，因为线程由操作系统管理，而协同程序由用户管理。数千个协程协同工作比数十个线程协同工作要好得多。

## Kotlin Coroutines 依赖项

在 [app 级文件](https://www.geeksforgeeks.org/android-build-gradle/) 中添加这些依赖项。

```kt
// dependencies to import in project
dependencies
{
  implementation "org.jetbrains.kotlinx:kotlinx-coroutines-core:x.x.x"
  implementation "org.jetbrains.kotlinx:kotlinx-coroutines-android:x.x.x"
}
```

> **注:** `x.x.x` 是 coroutine 的版本。

## Kotlin Coroutines 的例子

假设我们想从数据库中获取一些用户，并将其显示在屏幕上。为了从数据库中获取数据，我们必须执行网络调用，从数据库中获取用户，并将其显示在屏幕上。获取用户可以通过使用**回调**或**协程**来完成。

**使用回调:**

```kt
// pseudo kotlin code for demonstration
// involves a series of callbacks from fetchAndShowUser
// to fetchUser and then to showUser
fun fetchAndShowUser()
{
  fetchUser
  {
    user -> showUser(user)
  }
}
```

**使用协程:**

```kt
//pseudo kotlin code for demonstration
suspend fun fetchAndShowUser()
{
  // fetch on IO thread
  val user = fetchUser()
  // back on UI thread
  showUser(user)
}
```

如上所述，使用回调会降低代码的可读性，所以从可读性和性能的角度来看，使用 coroutines 更好。如上所述，除了没有回调之外，Coroutines 还有很多优点，比如它们不阻塞，创建简单且不昂贵。