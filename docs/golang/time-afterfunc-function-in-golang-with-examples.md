# Golang 中的 time.AfterFunc()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-afterfunc-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-afterfunc-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 Go 语言中的**AfterFunc()**函数用于等待经过的持续时间，之后，它在自己的 Go 例程中调用定义的函数“f”。 此外，该函数在**时间包**下定义。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func AfterFunc(d Duration, f func()) *Timer

```

这里，*Timer 是指向计时器的指针。

**返回值：**它返回一个*计时器*，然后在其 stop()方法的帮助下使用该计时器取消调用。

**示例 1：**

```go
// Golang program to illustrate the usage of
// AfterFunc() function

// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Main function
func main() {

    // Defining duration parameter of
    // AfterFunc() method
    DurationOfTime := time.Duration(3) * time.Second

    // Defining function parameter of
    // AfterFunc() method
    f := func() {

        // Printed when its called by the
        // AfterFunc() method in the time
        // stated above
        fmt.Println("Function called by "+
            "AfterFunc() after 3 seconds")
    }

    // Calling AfterFunc() method with its
    // parameter
    Timer1 := time.AfterFunc(DurationOfTime, f)

    // Calling stop method 
    // w.r.to Timer1
    defer Timer1.Stop()

    // Calling sleep method
    time.Sleep(10 * time.Second)
}
```

发帖主题：Re：Колибри0.7.8.0

在这里，输出在 3 秒后返回，然后返回的计时器使用 stop()方法取消对函数的调用。 然后，程序在休眠持续时间结束后退出。

**示例 2：**

```go
// Golang program to illustrate the usage of
// AfterFunc() function

// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Main function
func main() {

    // Creating channel using
    // make keyword
    mychan := make(chan int)

    // Calling AfterFunc() method
    // with its parameters
    time.AfterFunc(6*time.Second, func() {

        // Printed after stated duration
        // by AfterFunc() method is over
        fmt.Println("6 seconds over....")

        // loop stops at this point
        mychan <- 30
    })

    // Calling for loop
    for {

        // Select statement
        select {

        // Case statement
        case n := <-mychan:

            // Printed after the loop stops
            fmt.Println(n, "is arriving")
            fmt.Println("Done!")
            return

        // Returned by default
        default:

            // Printed until the loop stops
            fmt.Println("time to wait")

            // Sleeps for 3 seconds
            time.Sleep(3 * time.Second)
        }
    }
}
```

发帖主题：Re：Колибри0.7.8.0

在上面的例子中，在规定的持续时间结束之后，通道返回其输出，程序退出。