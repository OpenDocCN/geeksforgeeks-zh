# Golang 中的 `time.Nanoseconds()` 函数示例

> Original: [https://www.geeksforgeeks.org/time-nanoseconds-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-nanoseconds-function-in-golang-with-examples/)

在 Go 语言中，`time` 包提供了确定和查看时间的功能。Go 语言中的 `Nanoseconds()` 函数用于查找整数纳秒计数形式的持续时间。这个函数是在 `time` 包中定义的。在这里，你需要导入 `time` 包才能使用这些函数。

## 语法：

`func (d Duration) Nanoseconds() int64`

这里，`d` 是持续时间。

## 返回值：

返回 `int64` 形式的持续时间值。

## 示例 1：

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
    nano, _ := time.ParseDuration("8s")

    // Prints duration as int64
    fmt.Printf("Only %d nanoseconds of"+
        " task is remaining.", nano.Nanoseconds())
}
```

输出：

```go
Only 8000000000 nanoseconds of task is remaining.
```

## 示例 2：

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

输出：

```go
Only 587782576000000 nanoseconds of task is remaining.
```