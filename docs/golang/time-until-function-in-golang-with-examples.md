# Golang 中的 time.Until()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-until-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-until-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**Until()**函数保存时间值 t，用于评估到时间 t 的持续时间。此外，该函数在时间包中定义。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func Until(t Time) Duration

```

这里，t 是时间值。

**注意：**此方法是*t.Sub(time.Now())*的快捷方式。

**返回值：**返回到 t 的时长。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Until() function

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
    // of Until method
    t := time.Now()

    // Prints duration until t
    fmt.Println("Duration until t:", time.Until(t))
}
```

发帖主题：Re：Колибри0.7.0

```go
Duration until t: -230ns  // Can be different at different run times

```

这里是打印 t 之前的持续时间。 因此，它在不同的运行时间可以是不同的。

**示例 2：**

```go
// Golang program to illustrate the usage of
// Until() function

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
    // of Until method
    t := time.Now()

    // Calling Until method with its
    // parameter
    Duration := time.Until(t)

    // Prints duration until
    // t in nanoseconds 
    fmt.Println("duration until t in nanoseconds: ",
                           Duration.Nanoseconds())
}
```

发帖主题：Re：Колибри0.7.0

```go
duration until t in nanoseconds:  -340  // Can be different at different run times

```