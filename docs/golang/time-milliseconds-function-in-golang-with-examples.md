# Golang 中的 time.Milliseconds()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-milliseconds-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-milliseconds-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**毫秒()**函数用于查找整数毫秒计数形式的持续时间。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (d Duration) Milliseconds() int64

```

这里，d 是持续时间。

**返回值：**返回 int64 形式的持续时间值。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Milliseconds() function

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
    // of Milliseconds method
    milli, _ := time.ParseDuration("7s")

    // Prints duration as 
    // an integer milliseconds
    fmt.Printf("Only %d milliseconds of "+
      "task is remaining.", milli.Milliseconds())
}
```

发帖主题：Re：Колибри0.7.0

```go
Only 7000 milliseconds of task is remaining.

```

**示例 2：**

```go
// Golang program to illustrate the usage of
// Milliseconds() function

// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Calling main
func main() {

    // Defining duration of 
    // Milliseconds method
    milli, _ := time.ParseDuration("2h1m2s4545ns")

    // Prints duration as 
    // an integer milliseconds
    fmt.Printf("Only %d milliseconds of"+
     " task is remaining.", milli.Milliseconds())
}
```

发帖主题：Re：Колибри0.7.0

```go
Only 7262000 milliseconds of task is remaining.

```