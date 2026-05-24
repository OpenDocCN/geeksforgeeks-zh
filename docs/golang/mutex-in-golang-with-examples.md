# Golang 中的互斥体示例

> 原文:[https://www . geesforgeks . org/mutex-in-golang-with-examples/](https://www.geeksforgeeks.org/mutex-in-golang-with-examples/)

互斥体是一种用作锁定机制的方法，以确保在任何时间点都只有一个 Goroutine 访问代码的[关键部分](https://www.geeksforgeeks.org/g-fact-70/)。这样做是为了防止比赛情况发生。同步包包含互斥体。互斥体上定义的两种方法

*   锁
*   开启

在调用锁定和解锁之间出现的任何代码都将只由一个 Goroutine 执行。

```go
mutex.Lock() 

x = x + 1 // this statement be executed
          // by only one Goroutine 
          // at any point of time  

mutex.Unlock()

```

如果一个 Goroutine 已经有了锁，并且如果一个新的 Goroutine 试图获得锁，那么新的 Goroutine 将被停止，直到互斥体被解锁。为了理解这个概念，让我们首先理解一个具有比赛条件的程序。

### 带比赛条件的程序

这是一个遇到竞争条件的程序的例子

```go
// Program with race condition
package main  
import (  
    "fmt"
    "sync" // to import sync later on
)
var GFG  = 0

// This is the function we’ll run in every
// goroutine. Note that a WaitGroup must
// be passed to functions by pointer.  
func worker(wg *sync.WaitGroup) {  
    GFG = GFG + 1

    // On return, notify the 
    // WaitGroup that we’re done.
    wg.Done()
}
func main() { 

    // This WaitGroup is used to wait for 
    // all the goroutines launched here to finish. 
    var w sync.WaitGroup

    // Launch several goroutines and increment
    // the WaitGroup counter for each
    for i := 0; i < 1000; i++ {
        w.Add(1)        
        go worker(&w)
    }
    // Block until the WaitGroup counter
    // goes back to 0; all the workers 
    // notified they’re done.
    w.Wait()
    fmt.Println("Value of x", GFG)
}
```

**说明:**在上面的程序中，第 12 行的**工人**功能将 **GFG** 的值增加 1，然后调用**等待组**上的 **Done()** 通知其完成。**工人**功能被调用 1000 次。当多个戈鲁汀试图同时访问 **GFG** 的值时，这些戈鲁汀中的每一个同时运行，并且当试图增加第 13 行中的 **GFG** 时，比赛状态发生。由于竞争条件的原因，多次运行同一个程序每次会给出不同的输出。

> 请记住一件事，如果您将使用在线编译器检查上述程序的输出，由于确定性，您可能每次都会得到相同的输出(意味着没有竞争条件)。所以使用像 Visual Studio 或 CMD 这样的本地编译器来查看结果。

### 用互斥体解决上述问题

这是一个程序的例子，它说明了比赛条件是如何被固定的。

```go
// Program with race condition fixed by mutex
package main  
import (  
    "fmt"
    "sync" // to import sync later on
)
var GFG  = 0

// This is the function we’ll run in every
// goroutine. Note that a WaitGroup must
// be passed to functions by pointer.  
func worker(wg *sync.WaitGroup, m *sync.Mutex) { 
    // Lock() the mutex to ensure 
    // exclusive access to the state, 
    // increment the value,
    // Unlock() the mutex
    m.Lock() 
    GFG = GFG + 1
    m.Unlock()

    // On return, notify the 
    // WaitGroup that we’re done.
    wg.Done()
}
func main() { 
    // This WaitGroup is used to wait for 
    // all the goroutines launched here to finish. 
    var w sync.WaitGroup

    // This mutex will synchronize access to state.
    var m sync.Mutex

    // Launch several goroutines and increment
    // the WaitGroup counter for each
    for i := 0; i < 1000; i++ {
        w.Add(1)        
        go worker(&w, &m)
    }
    // Block until the WaitGroup counter
    // goes back to 0; all the workers 
    // notified they’re done.
    w.Wait()
    fmt.Println("Value of x", GFG)
}
```

**输出:**
值×1000

**说明:** *互斥体*是结构类型，变量 **m** 的类型**互斥体**是在第 31 行创建的。更改**工人**功能，以便在 **m.Lock()** 和 **m.Unlock()** 之间的第 18 行增加 **GFG** 的代码。现在，在任何时间点，只允许一个 Goroutine 执行这段代码，因此可以处理竞争条件。

互斥体的地址必须在第 37 行传递。如果互斥体是通过值传递的，那么每个 Goroutine 都有自己的互斥体副本，竞争条件仍然存在。