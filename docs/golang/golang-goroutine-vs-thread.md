# golang | gorroutine vs thread

> 哎哎哎:# t0]https://www . geeksforgeeks . org/golang-gorroutine-vs 线程/

**Goroutine:** 一个 [Goroutine](https://www.geeksforgeeks.org/goroutines-concurrency-in-golang/) 是一个函数或方法，它与你程序中的任何其他 Goroutine 同时独立执行。换句话说，Go 语言中的每个并发执行的活动都被称为 Goroutines。

**线程:**进程是操作系统的一部分，负责执行应用程序。在您的系统上执行的每个程序都是一个进程，为了在应用程序中运行代码，进程使用了一个称为线程的术语。线程是一个轻量级进程，或者换句话说，线程是一个在程序下执行代码的单元。所以每个程序都有逻辑，一个线程负责执行这个逻辑。

以下是 Goroutine 和 Thread 的一些区别:

| cor routine(例程) | Thread |
| Goroutine is managed by go runtime. | Operating system threads are managed by kernal. |
| goro tine does not depend on hardware. | Thread depends on hardware. |
| Golotines has an easy communication medium called channel. | Thread has no medium for easy communication. |
| Because of the existence of channel one, goro tine can communicate with other goro tine with low delay. | Due to the lack of simple communication media, the communication between threads is carried out with high delay. |
| goro tine has no ID, because go has no thread local storage. | Threads have their own unique ID, because they have thread local storage. |
| goro tines is cheaper than thread. | The cost of threads is higher than that of goroutine. |
| They made the reservation in cooperation. | They were booked first. |
| They start faster than threads. | Their startup time is slower than goroutines. |
| Golotin has a growing segmented stack room. | There is no sectional stack that can grow on the thread. |