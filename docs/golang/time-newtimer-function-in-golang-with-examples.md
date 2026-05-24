# Golang 中的 time.NewTimer()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-newtimer-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-newtimer-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**NewTimer()**函数用于创建一个新的计时器，该计时器至少在持续时间“d”之后在其频道上传输实际时间。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func NewTimer(d Duration) *Timer

```

这里，**Timer*是指向定时器的指针。

**返回值：**它返回一个通知计时器必须等待多长时间的通道。

**示例 1：**

```go
// Golang program to illustrate the usage of
// NewTimer() function

// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Main function
func main() {

    // Calling NewTimer method
    newtimer := time.NewTimer(5 * time.Second)

    // Notifying the channel
    <-newtimer.C

    // Printed after 5 seconds
    fmt.Println("Timer is inactivated")
}
```

发帖主题：Re：Колибри0.7.8.0

这里，上述输出是在运行代码 5 秒后打印的，因为在该规定时间之后，将通知通道定时器已停用。

**示例 2：**

```go
// Golang program to illustrate the usage of
// NewTimer() function

// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Main function
func main() {

    // Calling NewTimer method
    newtimer := time.NewTimer(time.Second)

    // Notifying channel under go function
    go func() {
        <-newtimer.C

        // Printed when timer is fired
        fmt.Println("timer inactivated")
    }()

    // Calling stop method to stop the
    // timer before inactivation
    stoptimer := newtimer.Stop()

    // If the timer is stopped then the
    // below string is printed
    if stoptimer {
        fmt.Println("The timer is stopped!")
    }

    // Calling sleep method to stop the
    // execution at last
    time.Sleep(4 * time.Second)
}
```

发帖主题：Re：Колибри0.7.8.0

在上面的方法中，计时器在停用之前被停止，因为这里调用 Stop 方法来停止计时器。 最后，采用休眠方式退出程序。