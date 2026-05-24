# 戈朗通道

> 原文:[https://www.geeksforgeeks.org/channel-in-golang/](https://www.geeksforgeeks.org/channel-in-golang/)

在 Go 语言中，通道是一个 goro tine 与另一个 goro tine 通信的媒介，这种通信是无锁的。或者换句话说，通道是一种允许一个 goro tine 向另一个 goro tine 发送数据的技术。默认情况下，通道是双向的，这意味着 goroutines 可以通过同一通道发送或接收数据，如下图所示:

![](img/eb77f537431fb65bf57349dc76b79423.png)

#### 创建频道

在 Go 语言中，通道是使用 chan 关键字创建的，它只能传输相同类型的数据，不同类型的数据不允许从同一通道传输。

**语法:**

```go
var Channel_name chan Type
```

您也可以使用 make()函数通过简写声明创建一个通道。

**语法:**

```go
channel_name:= make(chan Type)
```

**示例:**

```go
// Go program to illustrate
// how to create a channel
package main

import "fmt"

func main() {

    // Creating a channel
    // Using var keyword
    var mychannel chan int
    fmt.Println("Value of the channel: ", mychannel)
    fmt.Printf("Type of the channel: %T ", mychannel)

    // Creating a channel using make() function
    mychannel1 := make(chan int)
    fmt.Println("\nValue of the channel1: ", mychannel1)
    fmt.Printf("Type of the channel1: %T ", mychannel1)
}
```

**输出:**

```go
Value of the channel:  Type of the channel: chan int 
Value of the channel1:  0x432080
Type of the channel1: chan int 
```

#### 从通道发送和接收数据

在 Go 语言中，通道工作有两个主要操作，一个是发送，另一个是接收，这两个操作统称为通信。 **< -** 操作符的方向表示数据是接收还是发送。在信道中，默认情况下，发送和接收操作一直阻塞，直到另一端没有准备好。它允许 goroutine 在没有显式锁或条件变量的情况下相互同步。

1.  **Send operation:** The send operation is used to send data from one goroutine to another goroutine with the help of a channel. Values like int, float64, and bool can safe and easy to send through a channel because they are copied so there is no risk of accidental concurrent access of the same value. Similarly, strings are also safe to transfer because they are immutable. But for sending pointers or reference like a slice, map, etc. through a channel are not safe because the value of pointers or reference may change by sending goroutine or by the receiving goroutine at the same time and the result is unpredicted. So, when you use pointers or references in the channel you must make sure that they can only access by the one goroutine at a time.

    ```go
    Mychannel <- element
    ```

    上面的陈述表明数据(元素)在一个 **< -** 操作符的帮助下发送到通道(我的通道)。

2.  **Receive operation:** The receive operation is used to receive the data sent by the send operator.

    ```go
    element := <-Mychannel
    ```

    上面的语句表明元素从通道(我的通道)接收数据。如果收到的语句的结果不打算使用也是有效的语句。您也可以将 receive 语句写成:

    ```go
    <-Mychannel
    ```

**示例:**

```go
// Go program to illustrate send
// and receive operation
package main

import "fmt"

func myfunc(ch chan int) {

    fmt.Println(234 + <-ch)
}
func main() {
    fmt.Println("start Main method")
    // Creating a channel
    ch := make(chan int)

    go myfunc(ch)
    ch <- 23
    fmt.Println("End Main method")
}
```

**输出:**

```go
start Main method
257
End Main method

```

#### 关闭频道

您也可以借助 close()功能关闭频道。这是一个内置函数，并设置一个标志，表明没有更多的值将发送到这个通道。

**语法:**

```go
close()
```

您也可以使用 for range 循环关闭通道。这里，接收器 goroutine 可以在给定语法的帮助下检查通道是打开还是关闭:

```go
ele, ok:= <- Mychannel
```

这里，如果 ok 的值为真，这意味着通道打开，因此可以执行读取操作。如果的值为 false，这意味着通道关闭，因此不会执行读取操作。

**示例:**

```go
// Go program to illustrate how
// to close a channel using for
// range loop and close function
package main

import "fmt"

// Function
func myfun(mychnl chan string) {

    for v := 0; v < 4; v++ {
        mychnl <- "GeeksforGeeks"
    }
    close(mychnl)
}

// Main function
func main() {

    // Creating a channel
    c := make(chan string)

    // calling Goroutine
    go myfun(c)

    // When the value of ok is
    // set to true means the
    // channel is open and it
    // can send or receive data
    // When the value of ok is set to
    // false means the channel is closed
    for {
        res, ok := <-c
        if ok == false {
            fmt.Println("Channel Close ", ok)
            break
        }
        fmt.Println("Channel Open ", res, ok)
    }
}
```

**输出:**

```go
Channel Open  GeeksforGeeks true
Channel Open  GeeksforGeeks true
Channel Open  GeeksforGeeks true
Channel Open  GeeksforGeeks true
Channel Close  false

```

#### 要点

*   **阻塞发送和接收:**在通道中，当数据发送到一个通道时，控制在该发送语句中被阻塞，直到其他 goroutine 从该通道中读取。类似地，当一个通道接收到来自 goro tine 的数据时，读取语句块会一直持续到另一个 goro tine 语句。
*   **零值通道:**通道的零值为零。
*   **For loop in Channel:** A for loop can iterate over the sequential values sent on the channel until it closed.

    **语法:**

    ```go
    for item := range Chnl { 
         // statements..
    }

    ```

    **示例:**

    ```go
    // Go program to illustrate how to
    // use for loop in the channel

    package main

    import "fmt"

    // Main function
    func main() {

        // Creating a channel
        // Using make() function
        mychnl := make(chan string)

        // Anonymous goroutine
        go func() {
            mychnl <- "GFG"
            mychnl <- "gfg"
            mychnl <- "Geeks"
            mychnl <- "GeeksforGeeks"
            close(mychnl)
        }()

        // Using for loop
        for res := range mychnl {
            fmt.Println(res)
        }
    }
    ```

    **输出:**

    ```go
    GFG
    gfg
    Geeks
    GeeksforGeeks

    ```

*   **Length of the Channel:** In channel, you can find the length of the channel using *len() function*. Here, the length indicates the number of value queued in the channel buffer.

    **示例:**

    ```go
    // Go program to illustrate how to
    // find the length of the channel

    package main

    import "fmt"
    a
    // Main function
    func main() {

        // Creating a channel
        // Using make() function
        mychnl := make(chan string, 4)
        mychnl <- "GFG"
        mychnl <- "gfg"
        mychnl <- "Geeks"
        mychnl <- "GeeksforGeeks"

        // Finding the length of the channel
        // Using len() function
        fmt.Println("Length of the channel is: ", len(mychnl))
    }
    ```

    **输出:**

    ```go
    Length of the channel is:  4
    ```

*   **Capacity of the Channel:** In channel, you can find the capacity of the channel using cap() function. Here, the capacity indicates the size of the buffer.

    **示例:**

    ```go
    // Go program to illustrate how to
    // find the capacity of the channel

    package main

    import "fmt"

    // Main function
    func main() {

        // Creating a channel
        // Using make() function
        mychnl := make(chan string, 5)
        mychnl <- "GFG"
        mychnl <- "gfg"
        mychnl <- "Geeks"
        mychnl <- "GeeksforGeeks"

        // Finding the capacity of the channel
        // Using cap() function
        fmt.Println("Capacity of the channel is: ", cap(mychnl))
    }
    ```

    **输出:**

    ```go
    Capacity of the channel is:  5
    ```

*   **Channel 中的 select 和 case 语句:**在 go 语言中，Select 语句就像一个没有任何输入参数的 switch 语句。该 select 语句在通道中用于执行 case 块提供的多个操作中的一个操作。