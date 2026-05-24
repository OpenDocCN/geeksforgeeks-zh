# Golang 中的 time.NewTicker()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-newticker-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-newticker-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**NewTicker()**函数用于输出新的 Ticker，该新 Ticker 包含一个通道，以便传输具有 Duration 参数规定的周期的时间。 它有助于设置时间间隔或丢弃自动收报机的滴答声，以弥补收件人反应迟缓的情况。 这里，持续时间‘d’必须大于零，否则将发生死机错误。 您可以使用 stop()方法终止滚动条，以释放相关资源。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func NewTicker(d Duration) *Ticker

```

这里，“d”是持续时间，*Ticker 是指向 Ticker 的指针。 其中，Ticker 用于保持一个通道，该通道以一定的间隔提供时钟的“滴答声”。

**返回值：**它返回一个包含频道的新 Ticker。

**示例 1：**

```go
// Golang program to illustrate the usage of
// time.NewTicker() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Calling NewTicker method
    d := time.NewTicker(2 * time.Second)

    // Creating channel using make
    // keyword
    mychannel := make(chan bool)

    // Calling Sleep() methpod in go
    // function
    go func() {
        time.Sleep(7 * time.Second)

        // Setting the value of channel
        mychannel <- true
    }()

    // Using for loop
    for {

        // Select statement
        select {

        // Case statement
        case <-mychannel:
            fmt.Println("Completed!")
            return

        // Case to print current time
        case tm := <-d.C:
            fmt.Println("The Current time is: ", tm)
        }
    }
}
```

发帖主题：Re：Колибри0.7.8.0

这里，for loop 用于打印循环停止之前的当前时间，该时间是在代码中指定的“Tick”之后的规则间隔之后打印的。 这里是 2 秒。 因此，当前时间在规则间隔 2 秒后打印在上面。 在这里，自动报价器必须在三次后停止，因为限制是 7 秒，第三次自动售票机只剩下 1 秒了。