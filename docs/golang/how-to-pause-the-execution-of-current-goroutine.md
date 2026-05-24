# 如何暂停当前 Goroutine 的执行？

> 原文:[https://www . geesforgeks . org/如何暂停当前 goroutine 的执行/](https://www.geeksforgeeks.org/how-to-pause-the-execution-of-current-goroutine/)

一个 [Goroutine](https://www.geeksforgeeks.org/goroutines-concurrency-in-golang/) 是一个函数或方法，它与你程序中的任何其他 Goroutine 同时独立执行。换句话说，Go 语言中的每个并发执行的活动都被称为 Goroutines。所以在 Go 语言中，可以使用 **Sleep()** 功能暂停当前 goroutine 的执行。
此功能暂停当前 goro tine 至少指定的持续时间，完成指定的持续时间后，goro tine 自动唤醒并恢复工作。如果该函数的值为负或零，则该函数立即返回。它是在时间包下定义的，所以你必须在你的程序中导入时间包来访问睡眠功能。

**语法:**

```go
func Sleep(d_value Duration)
```

这里， **d_value** 代表你想休眠当前 goroutine 的持续时间。它可能以秒、毫秒、纳秒、微秒、分钟等为单位。让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Go program to illustrate how
// to put a goroutine to sleep
package main

import (
    "fmt"
    "time"
)

func show(str string) {

    for x := 0; x < 4; x++ {
        time.Sleep(300 * time.Millisecond)
        fmt.Println(str)
    }
}

// Main Function
func main() {

    // Calling Goroutine
    go show("Hello")

    // Calling function
    show("GeeksforGeeks")
}
```

**输出:**

```go
Hello
GeeksforGeeks
GeeksforGeeks
Hello
Hello
GeeksforGeeks
GeeksforGeeks

```

**例 2:**

```go
// Go program to illustrate how
// to put a goroutine to sleep
package main

import (
    "fmt"
    "time"
)

// Here, the value of Sleep function is zero
// So, this function return immediately.
func show(str string) {

    for x := 0; x < 4; x++ {

        time.Sleep(0 * time.Millisecond)
        fmt.Println(str)
    }
}

// Main Function
func main() {

    // Calling Goroutine
    go show("Hello")

    // Calling function
    show("Bye")
}
```

**输出:**

```go
Bye
Bye
Bye
Bye

```