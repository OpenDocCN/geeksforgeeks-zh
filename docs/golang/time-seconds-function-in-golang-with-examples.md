# Golang 中的 time.Seconds()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-seconds-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-seconds-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**s()**函数用于以浮点秒数的形式查找持续时间。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (d Duration) Seconds() float64

```

这里，d 是持续时间。

**返回值：**它以 float64 形式返回持续时间值。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Seconds() function

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
    // of Seconds method
    sec, _ := time.ParseDuration("7m")

    // Prints duration as a
    // floating point number
    fmt.Printf("Only %.1f seconds of "+
      "task is remaining.", sec.Seconds())
}
```

发帖主题：Re：Колибри0.7.0

```go
Only 420.0 seconds of task is remaining.

```

**示例 2：**

```go
// Golang program to illustrate the usage of
// Seconds() function

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
    // of Seconds method
    sec, _ := time.ParseDuration("3h8m756s6576.587ns")

    // Prints duration as a
    // floating point number
    fmt.Printf("Only %.1f seconds of "+
     "task is remaining.", sec.Seconds())
}
```

发帖主题：Re：Колибри0.7.0

```go
Only 12036.0 seconds of task is remaining.

```