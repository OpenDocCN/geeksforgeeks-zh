# Golang 中的 `time.Until()` 函数

> Original: [https://www.geeksforgeeks.org/time-until-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-until-function-in-golang-with-examples/)

在 Go 语言中，`time` 包提供了确定和查看时间的功能。`Until()` 函数接受一个时间值 `t`，用于计算到该时间 `t` 的持续时间。该函数在 `time` 包中定义，需要导入 `"time"` 包才能使用。

## 语法

```go
func Until(t Time) Duration
```

这里，`t` 是一个 `Time` 类型的值。

**注意：** 此方法是 `t.Sub(time.Now())` 的快捷方式。

**返回值：** 返回到 `t` 的 `Duration`。

## 示例 1

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

**输出：**

```go
Duration until t: -230ns  // Can be different at different run times
```

这里是打印 `t` 之前的持续时间。 因此，它在不同的运行时间可以是不同的。

## 示例 2

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

**输出：**

```go
duration until t in nanoseconds:  -340  // Can be different at different run times
```