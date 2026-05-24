# Golang 中的 time.Nanoseconds()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-nanoseconds-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-nanoseconds-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**纳秒()**函数用于查找整数纳秒计数形式的持续时间。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (d Duration) Nanoseconds() int64

```

这里，d 是持续时间。

**返回值：**返回 int64 形式的持续时间值。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Nanoseconds() function

// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Calling main
func main() {

    // Defining duration 
    // of Nanoseconds method
    nano, _ := time.ParseDuration("8s")

    // Prints duration as int64
    fmt.Printf("Only %d nanoseconds of"+
     " task is remaining.", nano.Nanoseconds())
}
```

发帖主题：Re：Колибри0.7.0

```go
Only 8000000000 nanoseconds of task is remaining.

```

**示例 2：**

```go
// Golang program to illustrate the usage of
// Nanoseconds() function

// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Calling main
func main() {

    // Defining duration of Nanoseconds method
    nano, _ := time.ParseDuration("56m7855s576567576ms")

    // Prints duration as int64
    fmt.Printf("Only %d nanoseconds of task"+
       " is remaining.", nano.Nanoseconds())
}
```

发帖主题：Re：Колибри0.7.0

```go
Only 587782576000000 nanoseconds of task is remaining.

```