# Golang 中的 time.hours()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-hours-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-hours-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**hr()**函数用于以浮点小时数的形式查找持续时间。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (d Duration) Hours() float64

```

这里，d 是持续时间。

**返回值：**它以 float64 形式返回持续时间。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Hours() function

// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Calling main
func main() {

    // Defining duration of Hours method
    hr, _ := time.ParseDuration("3h25m")

    // Prints duration as
    // floating point number
    fmt.Printf("Only %.1f hours of task is"+
                  " remaining.", hr.Hours())
}
```

发帖主题：Re：Колибри0.7.0

```go
Only 3.4 hours of task is remaining.

```

**示例 2：**

```go
// Golang program to illustrate the usage of
// Hours() function

// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Calling main
func main() {

    // Defining duration of Hours method
    hr, _ := time.ParseDuration("3h25m1200s6543356ms")

    // Prints duration as 
    // floating point number
    fmt.Printf("Only %.1f hours of "+
      "task is remaining.", hr.Hours())
}
```

发帖主题：Re：Колибри0.7.0

```go
Only 5.6 hours of task is remaining.

```