# 戈朗缓冲通道

> 原文:[https://www.geeksforgeeks.org/buffered-channel-in-golang/](https://www.geeksforgeeks.org/buffered-channel-in-golang/)

**通道**可以定义为 [**和**](https://www.geeksforgeeks.org/goroutines-concurrency-in-golang/) 进行通信的管道。类似于水在管道中从一端流到另一端，数据可以通过通道从一端发送，从另一端接收。默认情况下，信道是无缓冲的，这表明，如果有相应的接收端(< - chan)准备接收发送值，它们将只接受发送(chan < -)。缓冲通道允许接受有限数量的值，而这些值没有相应的接收器。可以用 buffe 创建一个通道。只有当缓冲区已满时，缓冲通道才会被阻塞。类似地，只有当缓冲区为空时，才会阻止从缓冲通道接收。

通过向指定缓冲区大小的 **make( )** 函数传递额外的容量参数，可以创建缓冲通道。

> **语法:**
> 
> ch := make(chan 类型，容量) // chan 定义通道类型

这里， ***容量*** 在上面的语法中应该大于 0 为一个通道才有一个缓冲区。默认情况下，无缓冲通道的容量为 0，因此它省略了容量参数。

**示例 1 :** 创建缓冲通道的代码。

## 去

```go
package main

import (
    "fmt"
)

func main() {

    // create a buffered channel 
    // with a capacity of 2.
    ch := make(chan string, 2)
    ch <- "geeksforgeeks"
    ch <- "geeksforgeeks world"
    fmt.Println(<-ch)
    fmt.Println(<-ch)
}
```

**输出:**

```go
geeksforgeeks
geeksforgeeks world

```

在上面的代码中，可以将 2 个字符串写入通道而不会被阻塞。它需要 2 个字符串到通道，并且不阻塞和打印结果。

**示例 2 :** 写入缓冲通道块的程序。

## 去

```go
package main

import (
    "fmt"
    "time"
)

func write(ch chan int) {
    for i := 0; i < 4; i++ {
        ch <- i
        fmt.Println("successfully wrote", i, "to ch")
    }
    close(ch)
}
func main() {

    // creates capacity of 2
    ch := make(chan int, 2)
    go write(ch)
    time.Sleep(2 * time.Second)
    for v := range ch {
        fmt.Println("read value", v, "from ch")
        time.Sleep(2 * time.Second)

    }
}
```

**输出:**

```go
successfully wrote 0 to ch
successfully wrote 1 to ch
read value 0 from ch
successfully wrote 2 to ch
read value 1 from ch
successfully wrote 3 to ch
read value 2 from ch
read value 3 from ch

```

在上面的代码中， ***写*** Goroutine 有一个 for 循环，将 0 到 3 的数字写到 ch 通道。该缓冲通道的容量为 2，因此写 Goroutine 能够立即将值 0 和 1 写入 ch 通道，然后将其阻塞，直到从 ch 通道读取至少一个值，如下所述:-

```go
successfully wrote 0 to ch
successfully wrote 1 to ch

```

之后，读取该值，然后再次休眠 2 秒钟，这个周期一直持续到 ch 关闭。因此，程序将在 2 秒后打印以下行，如下所示

```go
read value 0 from ch  
successfully wrote 2 to ch 

```

并且这将继续，直到所有值都被写入通道，并且它在 ***写入*** 戈罗廷中关闭。

### **缓冲戈朗通道**出现死锁

它被定义为程序在执行期间由于运行时死机而导致致命错误的情况。

**示例:**

## 去

```go
package main

import (
    "fmt"
)

func main() {
    ch := make(chan string, 2)
    ch <- "geeksforgeeks"
    ch <- "hello"
    ch <- "geeks"
    fmt.Println(<-ch)
    fmt.Println(<-ch)
}
```

在上面的代码中，由于通道已超出其容量，程序达到死锁状态，写入被阻止，并打印以下消息:

```go
fatal error: all goroutines are asleep - deadlock! 

goroutine 1 [chan send]: 
main.main() 
 /tmp/sandbox048494311/prog.go:11 +0x8d

```