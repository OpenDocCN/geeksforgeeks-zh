# Golang 中的 time.microsec()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-microseconds-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-microseconds-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**microsec()**函数用于查找整数微秒计数形式的持续时间。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (d Duration) Microseconds() int64

```

这里，d 是持续时间。

**返回值：**返回 int64 形式的持续时间值。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Microseconds() function

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
    // of Microseconds method
    micr, _ := time.ParseDuration("5m")

    // Prints duration as 
    // an integer microsecond
    fmt.Printf("Only %d Microseconds of task "+
          "is remaining.", micr.Microseconds())
}
```

发帖主题：Re：Колибри0.7.0

```go
Only 300000000 Microseconds of task is remaining.

```

**示例 2：**

```go
// Golang program to illustrate the usage of
// Microseconds() function

// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Calling main
func main() {

    // Defining duration of Microseconds method
    micr, _ := time.ParseDuration("1m1s576ms46ns")

    // Prints duration as 
    // an integer microsecond
    fmt.Printf("Only %d Microseconds of "+
     "task is remaining.", micr.Microseconds())
}
```

发帖主题：Re：Колибри0.7.0

```go
Only 61576000 Microseconds of task is remaining.

```