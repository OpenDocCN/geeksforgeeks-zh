# Golang 中的 `time.Minutes()` 函数示例

> Original: [https://www.geeksforgeeks.org/time-minutes-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-minutes-function-in-golang-with-examples/)

在 Go 语言中，`time` 包提供了确定和查看时间的功能。Go 语言中的 `Minutes()` 函数用于以浮点分钟数的形式查找持续时间。这个函数是在 `time` 包中定义的。在这里，您需要导入 `time` 包才能使用这些函数。

## 语法

```go
func (d Duration) Minutes() float64
```

这里，`d` 是持续时间。

## 返回值

它以 `float64` 形式返回持续时间值。

## 示例 1

```go
// Golang program to illustrate the usage of
// Minutes() function

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
    // of Minutes method
    min, _ := time.ParseDuration("34h")

    // Prints duration as a
    // floating point number
    fmt.Printf("Only %.1f minutes of"+
        " task is remaining.", min.Minutes())
}
```

输出：

```go
Only 2040.0 minutes of task is remaining.
```

## 示例 2

```go
// Golang program to illustrate the usage of
// Minutes() function

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
    // Minutes method
    min, _ := time.ParseDuration("3m4534s64376378ns")

    // Prints duration as a
    // floating point number
    fmt.Printf("Only %.1f minutes of"+
        " task is remaining.", min.Minutes())
}
```

输出：

```go
Only 78.6 minutes of task is remaining.
```