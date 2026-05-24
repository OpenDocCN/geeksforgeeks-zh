# Golang 中的 time.睡眠()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-sleep-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-sleep-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。
围棋语言中的**睡眠()**函数用于至少在规定的持续时间*d*内停止最新的围棋例程。 睡眠持续时间为负或为零将导致此方法立即返回。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func Sleep(d Duration)

```

这里，*d*是以秒为单位的睡眠持续时间。

**返回值：**它将最新的 GO 例程暂停指定的持续时间，然后在休眠结束后返回任何操作的输出。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Sleep() function

// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Main function
func main() {

    // Calling Sleep method
    time.Sleep(8 * time.Second)

    // Printed after sleep is over
    fmt.Println("Sleep Over.....")
}
```

发帖主题：Re：Колибри0.7.0

```go
Sleep Over.....

```

在这里，当调用 main 函数时运行上述代码之后，由于*睡眠*方法，所述操作将在给定的持续时间内停止，然后打印结果。

**示例 2：**

```go
// Golang program to illustrate the usage of
// Sleep() function

// Including main package
package main

// Importing time and fmt
import (
    "fmt"
    "time"
)

// Main function
func main() {

    // Creating channel using
    // make keyword
    mychan1 := make(chan string, 2)

    // Calling Sleep function of go
    go func() {
        time.Sleep(2 * time.Second)

        // Displayed after sleep overs
        mychan1 <- "output1"
    }()

    // Select statement
    select {

    // Case statement
    case out := <-mychan1:
        fmt.Println(out)

    // Calling After method
    case <-time.After(3 * time.Second):
        fmt.Println("timeout....1")
    }

    // Again Creating channel using
    // make keyword
    mychan2 := make(chan string, 2)

    // Calling Sleep method of go
    go func() {
        time.Sleep(6 * time.Second)

        // Printed after sleep overs
        mychan2 <- "output2"
    }()

    // Select statement
    select {

    // Case statement
    case out := <-mychan2:
        fmt.Println(out)

    // Calling After method
    case <-time.After(3 * time.Second):
        fmt.Println("timeout....2")
    }
}
```

发帖主题：Re：Колибри0.7.0

```go
output1
timeout....2

```

这里，在上面的代码中，由于超时持续时间(在 After()方法中)大于休眠时间(在 Sleep()方法中)，所以打印“output1”，因此在显示超时之前打印输出，但是在显示超时之后，下面的情况具有小于休眠时间的超时持续时间，因此在打印输出之前显示超时，因此显示为“Timeout…。 .2“。