# 戈朗的原子变量

> 原文:[https://www.geeksforgeeks.org/atomic-variable-in-golang/](https://www.geeksforgeeks.org/atomic-variable-in-golang/)

在 Go 语言中，使用**原子变量**来控制状态。这里，必须使用“同步/原子”包来使用这些变量。此外，它还防止了允许两个或更多的[戈鲁蒂尼](https://www.geeksforgeeks.org/goroutines-concurrency-in-golang/)访问相同来源的比赛条件。原子计数器有几种类型。用 go 语言管理状态的主要手段是通过[渠道](https://www.geeksforgeeks.org/channel-in-golang/)进行沟通。

**例 1:**

```go
// Golang program to illustrate the usage of
// atomic variable

// Including main package
package main

// Importing sync/atomic, math/rand,
// fmt, sync, and time
import (
    "fmt"
    "math/rand"
    "sync"
    "sync/atomic"
    "time"
)

// Using sync.WaitGroup in order to
// wait for a collection of
// goroutines to finish
var waittime sync.WaitGroup

// Declaring atomic variable
var atmvar int32

// Defining increment function
func hike(S string) {

    // For loop
    for i := 1; i < 7; i++ {

        // Calling sleep method with its duration
        // and also calling rand.Intn method
        time.Sleep(time.Duration((rand.Intn(5))) * time.Millisecond)

        // Calling AddInt32 method with its
        // parameter
        atomic.AddInt32(&atmvar, 1)

        // Prints output
        fmt.Println(S, i, "count ->", atmvar)
    }

    // Wait completed
    waittime.Done()
}

// Main function
func main() {

    // Calling Add method w.r.to
    // waittime variable
    waittime.Add(2)

    // Calling hike method with
    // values
    go hike("cat: ")
    go hike("dog: ")

    // Calling wait method
    waittime.Wait()

    // Prints the value of last count
    fmt.Println("The value of last count is :", atmvar)
}
```

**输出:**

```go
dog:  1 count -> 1
cat:  1 count -> 2
dog:  2 count -> 3
dog:  3 count -> 4
cat:  2 count -> 5
cat:  3 count -> 6
cat:  4 count -> 7
cat:  5 count -> 8
cat:  6 count -> 9
dog:  4 count -> 10
dog:  5 count -> 11
dog:  6 count -> 12
The value of last count is : 12

```

在上面的方法中，原子变量的类型是 int32。在这里，*兰特。Intn()方法*用于打印随机整数，直到循环停止。之后，使用 *AddInt32* 方法，将原子变量与另一个 Int32 数相加，然后在计数中返回。

**例 2:**

```go
// Golang program to illustrate the usage of
// AfterFunc() function

// Including main package
package main

// Importing sync/atomic, fmt,
// and sync
import (
    "fmt"
    "sync"
    "sync/atomic"
)

// Calling main
func main() {

    // Declaring atomic variable
    var atmvar uint32

    // Using sync.WaitGroup in order to
    // wait for a collection of
    // goroutines to finish
    var wait sync.WaitGroup

    // For loop
    for i := 0; i < 30; i += 2 {

        // Calling Add method
        wait.Add(1)

        // Calling AddUint32 method under
        // go function
        go func() {
            atomic.AddUint32(&atmvar, 2)

            // Wait completed
            wait.Done()
        }()
    }

    // Calling wait method
    wait.Wait()

    // Prints atomic variables value
    fmt.Println("atmvar:", atmvar)
}
```

**输出:**

```go
atmvar: 30

```

在上面的方法中，原子变量是 uint32 类型。这里，在 for 循环下使用 AddUint32()方法，该方法添加其参数，直到循环停止，然后返回原子变量的值。