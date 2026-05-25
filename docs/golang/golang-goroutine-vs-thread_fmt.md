# golang | goroutine vs thread

> 哎哎哎: [https://www.geeksforgeeks.org/golang-goroutine-vs-thread/](https://www.geeksforgeeks.org/golang-goroutine-vs-thread/)

## `Goroutine`
一个 [Goroutine](https://www.geeksforgeeks.org/goroutines-concurrency-in-golang/) 是一个函数或方法，它与你程序中的任何其他 Goroutine 同时独立执行。换句话说，Go 语言中的每个并发执行的活动都被称为 Goroutines。

## `Thread`
进程是操作系统的一部分，负责执行应用程序。在您的系统上执行的每个程序都是一个进程，为了在应用程序中运行代码，进程使用了一个称为线程的术语。线程是一个轻量级进程，或者换句话说，线程是一个在程序下执行代码的单元。所以每个程序都有逻辑，一个线程负责执行这个逻辑。

以下是 Goroutine 和 Thread 的一些区别：

| Goroutine | Thread |
| :--- | :--- |
| Goroutine 由 Go runtime 管理。 | 操作系统线程由内核管理。 |
| Goroutine 不依赖于硬件。 | 线程依赖于硬件。 |
| Goroutine 有一个简单的通信媒介，称为 `channel`。 | 线程没有简单的通信媒介。 |
| 由于 `channel` 的存在，Goroutine 可以以低延迟与其他 Goroutine 通信。 | 由于缺乏简单的通信媒介，线程之间的通信以高延迟进行。 |
| Goroutine 没有 ID，因为 Go 没有线程本地存储。 | 线程有自己唯一的 ID，因为它们有线程本地存储。 |
| Goroutine 比线程更廉价。 | 线程的成本比 Goroutine 更高。 |
| 它们以协作式进行调度。 | 它们以抢占式进行调度。 |
| 它们的启动比线程更快。 | 它们的启动时间比 Goroutine 更慢。 |
| Goroutine 拥有可增长的分段栈空间。 | 线程上没有可增长的分段栈。 |