# 操作系统用 Java 代替 C 的比较

> 原文：[`https://www.geeksforgeeks.org/comparison-on-using-java-for-an-operating-system-instead-of-c/`](https://www.geeksforgeeks.org/comparison-on-using-java-for-an-operating-system-instead-of-c/)

[`Java`](https://www.geeksforgeeks.org/java/) 是一种提供内存安全的托管语言。
在 [`Java`](https://www.geeksforgeeks.org/java/) 中，指针是不存在的，所以我们不能对函数指针做指针运算。应用程序可以通过类对象调用类中定义的方法。在 [`Java`](https://www.geeksforgeeks.org/java/) 中，我们不能对一个对象进行不安全的类型转换来用其他东西覆盖方法指针。超出界限的数组访问在 [`Java`](https://www.geeksforgeeks.org/java/) 中引发运行时异常，因此返回地址损坏是不可能的。

现在，让我们看看通过 [`Java`](https://www.geeksforgeeks.org/java/) 实现的操作系统的一些重要方面。

## 内存隔离
在 [`Java`](https://www.geeksforgeeks.org/java/) 中，内存只能通过对象访问。[`Java`](https://www.geeksforgeeks.org/java/) 应用程序不能访问对象外部的内存。虚拟内存没有抽象到应用程序中。由于这些原因，我们不需要额外的硬件支持（分段/页表）来进行进程分配。不需要页表或特权环。内核本身是一个 [`Java`](https://www.geeksforgeeks.org/java/) 进程，所以内核和不可信的应用程序都在 `ring-0` 中执行。

## 系统调用
要执行系统调用，我们需要切换到内核进程。切换到不同的进程不需要页表切换。因此，系统调用处理程序只是一个上下文切换例程，它复制内核地址空间中的系统调用参数，并直接跳转到系统调用处理程序。

## 进程间通信（IPC）
[`IPC`](https://www.geeksforgeeks.org/ipc/) 类似于系统调用处理程序。复制消息后，上下文切换方法需要在目标进程中调用接收例程。因此，这比 [`Linux`](https://www.geeksforgeeks.org/linux-kernel/) 和 [`Windows`](https://www.geeksforgeeks.org/windows/) 更好，在 [`Linux`](https://www.geeksforgeeks.org/linux-kernel/) 和 [`Windows`](https://www.geeksforgeeks.org/windows/) 中，我们必须进行两次环形转换和一次上下文切换来调度目标例程。

## 设备驱动程序
每个设备驱动程序都可以分配给一个单独的 [`Java`](https://www.geeksforgeeks.org/java/) 进程。设备驱动程序可以通过系统调用与内核通信。

但是，现有的操作系统不是用 [`Java`](https://www.geeksforgeeks.org/java/) 编写的。这是因为，[`Java`](https://www.geeksforgeeks.org/java/) 不是一种高效的语言，特别是由于垃圾收集会导致任意的延迟。

因此，所有的操作系统都广泛使用 [`C`](https://www.geeksforgeeks.org/c-programming-language/) 语言，而不是 [`Java`](https://www.geeksforgeeks.org/java/)。