# Golang 中的 `time.Since()` 函数示例

> Original: [https://www.geeksforgeeks.org/time-since-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-since-function-in-golang-with-examples/)

在 Go 语言中，`time` 包提供了确定和查看时间的功能。`time` 包中的 `Since()` 函数保存时间值，用于计算与当前时间的差值。这个函数是在 `time` 包中定义的，因此需要导入 `time` 包才能使用。

## 语法：

```go
func Since(t Time) Duration
```

这里，`t` 是一个 `Time` 类型的值。

**注意：** 此方法是 `time.Now().Sub(t)` 的快捷方式。

## 返回值：

返回一个 `Duration` 类型的值。

## 示例 1：

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

**输出：**

```go
time elapse: 210ns // Can be different at different run times
```

这里打印的是从 `now` 所代表的时间点到当前时间之间经过的时间。因此，它在不同的运行时刻可以是不同的。

## 示例 2：

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

**输出：**

```go
time elapse in nanoseconds: 351 // Can be different at different run times
```