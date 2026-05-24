# Golang 中的 time.Ticker.Stop()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-ticker-stop-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-ticker-stop-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**NewTicker()**函数用于禁用滚动条。 因此，在调用 stop()方法之后，不会再传输任何记号。 并且它不关闭该通道，以避免从该通道同时进行的 GO-例程读取不会看到不准确的“滴答”。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (t *Ticker) Stop()

```

这里，“t”是指向 Ticker 的指针。 其中，Ticker 用于保持以一定间隔提供时钟“滴答声”的通道。

**返回值：**它在调用 stop()方法之前返回所述操作的输出，因为在调用它之后，滚动条被关闭。

**示例：**

```go
// Golang program to illustrate the usage of
// time.Ticker.Stop() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Calling NewTicker method
    Ticker := time.NewTicker(2 * time.Second)

    // Creating channel using make
    // keyword
    mychannel := make(chan bool)

    // Go function
    go func() {

        // Using for loop
        for {

            // Select statement
            select {

            // Case statement
            case <-mychannel:
                return

            // Case to print current time
            case tm := <-Ticker.C:
                fmt.Println("The Current time is: ", tm)
            }
        }
    }()

    // Calling Sleep() method
    time.Sleep(7 * time.Second)

    // Calling Stop() method
    Ticker.Stop()

    // Setting the value of channel
    mychannel <- true

    // Printed when the ticker is turned off
    fmt.Println("Ticker is turned off!")
}
```

发帖主题：Re：Колибри0.7.8.0

这里，首先创建 Ticker，然后创建传输时间的通道。 之后，使用 for 循环打印当前时间，然后调用 Ticker.Stop()方法并关闭滚动条。