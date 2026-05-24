# Golang 中的 time.Since()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-since-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-since-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 围棋语言中的**from()**函数保存时间值，用于计算与实际时间的差异。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func Since(t Time) Duration

```

这里，t 是时间值。

**注意：**此方法是*时间的快捷方式。Now().Sub(T)*。

**返回值：**返回持续时间值。

**示例 1：**

```go
// Golang program to illustrate in Golang

// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Calling main
func main() {

    // Defining time value
    // of Since method
    now := time.Now()

    // Prints time elapse
    fmt.Println("time elapse:",
             time.Since(now))
}
```

发帖主题：Re：Колибри0.7.0

```go
time elapse: 210ns // Can be different at different run times

```

这里打印的是从现在到当前时间之间经过的时间。 因此，它在不同的运行时间可以是不同的。

**示例 2：**

```go
// Golang program to illustrate in Golang

// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Calling main
func main() {

    // Defining time value 
    // of Since method
    timevalue := time.Now()

    // Calling Since method
    // with its parameter
    Duration := time.Since(timevalue)

    // Prints time elapse in nanoseconds
    fmt.Println("time elapse in nanoseconds:",
                   Duration.Nanoseconds())
}
```

发帖主题：Re：Колибри0.7.0

```go
time elapse in nanoseconds: 351 // Can be different at different run times

```