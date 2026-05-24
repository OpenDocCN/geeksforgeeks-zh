# 在 Golang 使用 WaitGroup

> Original: [https://www.geeksforgeeks.org/using-waitgroup-in-golang/](https://www.geeksforgeeks.org/using-waitgroup-in-golang/)

对 Golang 来说，围棋程序是一个很好的卖点，这让它成为了许多开发者的选择。 在本文中，我们将看到这些[**Goroutine**](https://www.geeksforgeeks.org/goroutines-concurrency-in-golang/)的一个常见问题，并尝试解决它。

让我们看一个简单的代码片段来说明这个问题，

## go

```go
package main

import "fmt"

func runner1() {
    fmt.Print("\nI am first runner")
}

func runner2() {
    fmt.Print("\nI am second runner")
}

func execute() {
    go runner1()
    go runner2()

}

func main() {

    // Launching both the runners
    execute()
}
```

正如您刚才看到的，输出中没有任何内容，这是因为一旦启动了两个 goroutine，您的主函数就被终止了。 并执行 Golang 中的每个程序，直到主函数未终止。 那么，我们能做些什么来解决这个问题呢？

**1.**我们可以在启动跑步器后等待一段时间，为此，我们将使用“**Time**”Packages 函数“**Slear**”，它会在给定的时间内暂停功能的执行，

## Go

```go
package main

import (
    "fmt"
    "time"
)

func runner1() {
    fmt.Print("\nI am first runner")
}

func runner2() {
    fmt.Print("\nI am second runner")
}

func execute() {
    go runner1()
    go runner2()

}

func main() {

    // Launching both the runners
    execute()
    time.Sleep(time.Second)
}
```

。

## Go

```go
package main

import (
    "fmt"
    "time"
)

func runner1() {
    fmt.Print("\nI am first runner")
}

func runner2() {
    fmt.Print("\nI am second runner")
}

func execute() {
    go runner1()
    go runner2()

}

func main() {

    // Launching both the runners
    execute()
    time.Sleep(time.Second)
}
```

发帖主题：Re：Колибри0.7.8.0

我们只是解决了这个问题，在启动我们的跑步器之后，我们等待了一秒钟，所以我们的主要功能是休眠(阻塞)1 秒。 在此期间，所有围棋例程都成功执行。 但 Golang 是一种速度很快的语言，仅打印 2 个字符串不需要 1 秒。

问题是，我们的执行器在一段时间内执行，所以我们不必要地阻塞程序 1 秒。 在本例中，这似乎不是一个严重的问题，但如果您创建一台**生产**级服务器，该服务器将同时为 1000 个请求提供服务，这将是一个大问题。

**2.**让我们使用另一个 Golang 的标准库原语“**sync.WaitGroup**”。 **WaitGroup**实际上是一种计数器，它会阻止函数(或者可以说是 Goroutine)的执行，直到**其内部计数器变为 0**。

### 它是怎么工作的？

WaitGroup 导出 3 种方法。

<figure class="table">

| 1. | **Add(Int)** | It will wait for the group counter to increase the given integer value. |
| 2 个 | **完成()** | If it subtracts the WaitGroup counter by 1, we will use it to indicate the termination of the Goroutine. |
| 3. | **等待()** | It blocks execution until its internal counter becomes 0. |

</figure>

**注意**：WaitGroup 是并发安全的，因此将指向它的指针作为 Groutines 的参数传递是安全的。

## 转

```go
package main

import (
    "fmt"
    "sync"
)

func runner1(wg *sync.WaitGroup) {
    defer wg.Done() // This decreases counter by 1
    fmt.Print("\nI am first runner")

}

func runner2(wg *sync.WaitGroup) {
    defer wg.Done()
    fmt.Print("\nI am second runner")
}

func execute() {
    wg := new(sync.WaitGroup)
    wg.Add(2)

    // We are increasing the counter by 2
    // because we have 2 goroutines
    go runner1(wg)
    go runner2(wg)

    // This Blocks the execution
    // until its counter become 0
    wg.Wait()
}

func main() {
    // Launching both the runners
    execute()
}
```

发帖主题：Re：Колибри0.7.8.0

输出是相同的，但是我们的输出程序在 1 秒内不会阻塞。 模式，我们在上面向您展示了用 Golang 编写并发代码的常见做法。