# Goroutines–Golang 中的并发

> 原文:[https://www . geesforgeks . org/goro tines-concurrency-in-golang/](https://www.geeksforgeeks.org/goroutines-concurrency-in-golang/)

Go 语言提供了一个被称为 Goroutines 的特殊功能。Goroutine 是一个[函数](https://www.geeksforgeeks.org/functions-in-go-language/)或方法，它与程序中的任何其他 Goroutine 同时独立执行。换句话说，Go 语言中的每个并发执行的活动都被称为 Goroutines。你可以把戈鲁丁线看作是一根重量轻的线。与线程相比，创建 Goroutines 的成本非常小。每个程序至少包含一个戈鲁丁，而那个戈鲁丁被称为**主戈鲁丁**。所有的戈鲁汀都在主戈鲁汀下工作，如果主戈鲁汀终止，那么程序中的所有戈鲁汀也终止。Goroutine 总是在后台工作。

#### 如何创建一个 Goroutine？

您可以创建自己的 Goroutine，只需使用 go 关键字作为函数或方法调用的前缀，如下语法所示:

**语法:**

```go
func name(){
// statements
}

// using go keyword as the 
// prefix of your function call
go name()

```

**示例:**

```go
// Go program to illustrate
// the concept of Goroutine
package main

import "fmt"

func display(str string) {
    for w := 0; w < 6; w++ {
        fmt.Println(str)
    }
}

func main() {

    // Calling Goroutine
    go display("Welcome")

    // Calling normal function
    display("GeeksforGeeks")
}
```

**输出:**

```go
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks

```

在上面的例子中，我们简单地创建了一个 *display()* 函数，然后以两种不同的方式调用这个函数首先一个是 Goroutine，即 *go display(【欢迎】)*，另一个是普通函数，即*display(【geeks forgeeks】)*。但是有一个问题，它只显示正常函数的结果，不显示 Goroutine 的结果，因为当一个新的 Goroutine 执行时，Goroutine 调用会立即返回。控件不会像正常函数一样等待 Goroutine 完成它们的执行，它们总是在 Goroutine 调用后前进到下一行，并忽略 Goroutine 返回的值。因此，为了正确执行 Goroutine，我们在程序中做了一些更改，如下面的代码所示:

**修改例:**

```go
// Go program to illustrate the concept of Goroutine
package main

import (
    "fmt"
    "time"
)

func display(str string) {
    for w := 0; w < 6; w++ {
        time.Sleep(1 * time.Second)
        fmt.Println(str)
    }
}

func main() {

    // Calling Goroutine
    go display("Welcome")

    // Calling normal function
    display("GeeksforGeeks")
}
```

**输出:**

```go
Welcome
GeeksforGeeks
GeeksforGeeks
Welcome
Welcome
GeeksforGeeks
GeeksforGeeks
Welcome
Welcome
GeeksforGeeks
GeeksforGeeks

```

我们在程序中增加了 *Sleep()方法*，使主 Goroutine 在新 Goroutine 执行的 1 秒之间休眠 1 秒，在屏幕上显示*欢迎*，1 秒后终止主 Goroutine 重新调度并执行其操作。这个过程一直持续到 *z < 6* 的值，之后主戈罗廷终止。在这里，Goroutine 和正常功能同时工作。

#### 戈鲁汀的优点

*   Goroutines 比线程便宜。
*   Goroutine 存储在堆栈中，堆栈的大小可以根据程序的要求而增减。但是在线程中，堆栈的大小是固定的。
*   goro tines 可以使用通道进行通信，这些通道是专门为防止使用 goro tines 访问共享内存时出现争用情况而设计的。
*   假设一个程序有一个线程，这个线程有许多与其相关联的 Goroutines。如果任何一个 Goroutine 由于资源需求而阻塞了线程，那么所有剩余的 Goroutine 将被分配给一个新创建的操作系统线程。所有这些细节对程序员来说都是隐藏的。

#### 匿名 Goroutine

在 go 语言中，您也可以为匿名函数启动 Goroutine，或者换句话说，您可以通过使用 Go 关键字作为该函数的前缀来创建匿名 Goroutine，如下语法所示:

**语法:**

```go
// Anonymous function call
go func (parameter_list){
// statement
}(arguments)

```

**示例:**

```go
// Go program to illustrate how
// to create an anonymous Goroutine
package main

import (
    "fmt"
    "time"
)

// Main function
func main() {

    fmt.Println("Welcome!! to Main function")

    // Creating Anonymous Goroutine
    go func() {

        fmt.Println("Welcome!! to GeeksforGeeks")
    }()

    time.Sleep(1 * time.Second)
    fmt.Println("GoodBye!! to Main function")
}
```

**输出:**

```go
Welcome!! to Main function
Welcome!! to GeeksforGeeks
GoodBye!! to Main function

```