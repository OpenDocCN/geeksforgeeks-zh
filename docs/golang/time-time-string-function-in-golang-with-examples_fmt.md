# Golang 中的 `time.Time.String()` 函数

> Original: [https://www.geeksforgeeks.org/time-time-string-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-string-function-in-golang-with-examples/)

在 Go 语言中，`time` 包提供了确定和查看时间的功能。`Time.String()` 函数用于生成一个经过格式化的时间字符串。该函数在 `time` 包中定义，使用前需要导入 `time` 包。

## 语法

```go
func (t Time) String() string
```

这里，`t` 是规定的时间。

## 注意

如果规定时间的时钟读数是单调的，则作为输出返回的字符串包括最后一个字段，即 `m=±value`。其中，值是以十进制秒数排列的不变时钟读数。

## 返回值

返回通过格式化字符串格式化后的时间。

## 示例 1

```go
// Golang program to illustrate the usage of
// Time.String() function

// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Calling main
func main() {

    // Defining the time for String method
    Time := time.Date(2020, 11, 14, 10, 45, 16, 0, time.UTC)

    // Calling String method
    t := Time.String()

    // Prints output
    fmt.Printf("The time without nanoseconds is: %v\n", t)
}
```

输出：

```
The time without nanoseconds is: 2020-11-14 10:45:16 +0000 UTC
```

## 示例 2

```go
// Golang program to illustrate the usage of
// Time.String() function

// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Calling main
func main() {

    // Defining the time for String method
    Time := time.Date(2020, 11, 14, 36, 45, 16, 36, time.UTC)

    // Calling String method
    t := Time.String()

    // Prints output
    fmt.Printf("The time with nanoseconds is: %v\n", t)
}
```

输出：

```
The time with nanoseconds is: 2020-11-15 12:45:16.000000036 +0000 UTC
```

这里，上面代码中所述的小时超出了通常的范围，但它是标准化的，而转换和纳秒也包括在上面所述的时间中。