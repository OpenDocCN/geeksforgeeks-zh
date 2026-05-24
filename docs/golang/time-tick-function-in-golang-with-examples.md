# Golang 中的 time.Tick()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-tick-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-tick-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**tick()**函数是*NewTicker*函数的实用程序包装。 它只允许访问滴答通道。 此外，*tick*对不需要关闭 Ticker 的客户端很有帮助。 如果所述持续时间小于或等于 0，则 tick 方法返回 nil。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func Tick(d Duration) <-chan Time

```

这里，*d*是自动收报机滴答的持续时间，*chan*是自动收报机的计时通道。

**注：**自动收报机用于在规定的时间间隔内频繁地做某事。

**返回值：**返回固定时间间隔后的当前日期和实际时间。 如果 d<=0，则返回 nil。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Tick() function

// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Defining UTCtime
func UTCtime() string {
    return ""
}

// Main function
func main() {

    // Calling Tick method
    // using range keyword
    for tick := range time.Tick(3 * time.Second) {

        // Prints UTC time and date
        fmt.Println(tick, UTCtime())
    }
}
```

发帖主题：Re：Колибри0.7.8.0

在这里，我们使用了 Range 关键字来迭代通道。 在这里，当前日期和时间是在规则的时间间隔之后返回的。 因此，在不同的运行中，输出是不同的。 在这里，循环不会停止，直到你终止它。

**示例 2：**

```go
// Golang program to illustrate the usage of
// Tick() function
// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Defining UTCtime
func UTCtime() string {
    return ""
}

// Main function
func main() {

    // Calling Tick method using range
    // keyword
    for tick := range time.Tick(-1 * time.Second) {

        // Prints UTC time and date
        fmt.Println(tick, UTCtime())
    }
}
```

发帖主题：Re：Колибри0.7.8.0

这里，在上面的代码中，声明的持续时间为负值，因此返回 nil 并发生错误。