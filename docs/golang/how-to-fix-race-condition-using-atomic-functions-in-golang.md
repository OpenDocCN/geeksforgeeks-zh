# 如何在 Golang 中使用原子函数修复种族条件？

> 原文:[https://www . geesforgeks . org/如何使用 golang 中的原子函数修复比赛条件/](https://www.geeksforgeeks.org/how-to-fix-race-condition-using-atomic-functions-in-golang/)

在一个系统中执行的两个或多个进程，如果有并发和访问共享数据的错觉，可能会试图同时更改共享数据。系统中的这种情况称为竞争情况。要查看 Golang 中比赛状态的示例代码，可以参考[这篇](https://www.geeksforgeeks.org/mutex-in-golang-with-examples/)文章。
Golang 中的原子包提供了低级锁定机制，用于同步对指针和整数等的访问。原子/同步包功能用于修复争用情况。

**示例:**

```go
// Golang program to fix the race
// condition using atomic package
package main

import (
    "fmt"
    "runtime"
    "sync"
    "sync/atomic"
)

// All goroutines will increment  variable c
// waitgroup is waiting for the completion
// of program.
var (
    c         int32
    waitgroup sync.WaitGroup
)

func main() {

    // with the help of Add() function add
    // one for each goroutine
    // a count of total 3
    waitgroup.Add(3)

    // increment with the help
    // of increment() function
    go increment("geeks")
    go increment("for")
    go increment("geeks")

    // waiting for completion
    // of goroutines.
    waitgroup.Wait()

    // print the counter
    fmt.Println("Counter:", c)

}

func increment(name string) {

    // Done() function used
    // to tell that it is done.
    defer waitgroup.Done()

    for range name {

        // Atomic Functions
        // for fix race condition
        atomic.AddInt32(&c, 1)

        // enter thread in the line by line
        runtime.Gosched()
    }
}
```

**输出:**

```go
Counter: 13

```

在这里，你可以看到我们正在使用**原子。AddInt32()** 函数同步整数值的相加，这样一次只允许一个 goroutine 完成相加操作。记住一件事，总是使用在线编译器检查这样一个程序的输出，因为由于确定性的本质，你可能每次都得到相同的输出(意味着没有竞争条件)。所以使用像 Visual Studio 或 CMD 这样的本地编译器来查看结果。