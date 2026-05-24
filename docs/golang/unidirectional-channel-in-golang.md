# Golang 中的单向信道

> Original: [https://www.geeksforgeeks.org/unidirectional-channel-in-golang/](https://www.geeksforgeeks.org/unidirectional-channel-in-golang/)

正如我们所知道的，通道是并发运行的 Goroutine 之间的通信媒介，以便它们可以相互发送和接收数据。 默认情况下，通道是双向的，但您也可以创建单向通道。 只能接收数据的通道或只能发送数据的通道是单向通道。 还可以借助 make()函数创建单向通道，如下所示：

```go
// Only to receive data
c1:= make(<- chan bool)

// Only to send data
c2:= make(chan<-bool

```

**示例 1：**

```go
// Go program to illustrate the concept
// of the unidirectional channel
package main

import "fmt"

// Main function
func main() {

    // Only for receiving
    mychanl1 := make(<-chan string)

    // Only for sending
    mychanl2 := make(chan<- string)

    // Display the types of channels
    fmt.Printf("%T", mychanl1)
    fmt.Printf("\n%T", mychanl2)
}
```

发帖主题：Re：Колибри0.7.8.0

#### 双向通道转换为单向通道

在围棋语言中，您可以将双向通道转换为单向通道，或者换句话说，您可以将双向通道转换为只接收或只发送通道，但反之亦然。 如以下程序所示：

**示例：**

```go
// Go program to illustrate how to convert
// bidirectional channel into the
// unidirectional channel
package main

import "fmt"

func sending(s chan<- string) {
    s <- "GeeksforGeeks"
}

func main() {

    // Creating a bidirectional channel
    mychanl := make(chan string)

    // Here, sending() function convert
    // the bidirectional channel
    // into send only channel
    go sending(mychanl)

    // Here, the channel is sent 
    // only inside the goroutine
    // outside the goroutine the 
    // channel is bidirectional
    // So, it print GeeksforGeeks
    fmt.Println(<-mychanl)
}
```

发帖主题：Re：Колибри0.7.8.0

**单向通道的使用：**单向通道用于提供程序的类型安全性，使程序产生的错误更少。 或者，当您想要创建只能发送或接收数据的通道时，也可以使用单向通道。