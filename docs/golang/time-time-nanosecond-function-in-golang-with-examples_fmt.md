# Golang 中的 `Time.Nanosecond()` 函数示例

> Original: [https://www.geeksforgeeks.org/time-time-nanosecond-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-nanosecond-function-in-golang-with-examples/)

在 Go 语言中，`time` 包提供了确定和查看时间的功能。`Time.Nanosecond()` 函数用于查找 `t` 提供的秒内的纳秒偏移量，范围为 [0, 999999999]。这个函数是在 `time` 包中定义的，因此需要导入 `time` 包才能使用。

## 语法

```go
func (t Time) Nanosecond() int
```

这里，`t` 是规定的时间。

## 返回值

它返回 `t` 提供的秒内的纳秒偏移量。

## 示例 1

```go
// Golang program to illustrate the usage of
// Time.Nanosecond() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring t in UTC
    t := time.Date(2017, 23, 5, 11,
              51, 04, 30, time.UTC)

    // Calling Nanosecond method
    nano := t.Nanosecond()

    // Prints nanoseconds as specified
    fmt.Printf("The stated nanoseconds "+
              "specified is: %v\n", nano)
}
```

## 示例 2

```go
// Golang program to illustrate the usage of
// Time.Nanosecond() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring t in UTC
    t := time.Date(2017, 34, 56, 78,
      87, 97, 687678678685757, time.UTC)

    // Calling Nanosecond method
    nano := t.Nanosecond()

    // Prints nanoseconds as specified
    fmt.Printf("The stated nanoseconds "+
              "specified is: %v\n", nano)
}
```

在这里，上面代码中声明的纳秒超出了通常的范围，但在转换时会进行标准化。