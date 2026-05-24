# Golang 中的 time.Unix()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-unix-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-unix-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**unix()**函数用于生成与从 1970 年 1 月 1 日起以 UTC 表示的 Unix 时间相关的本地时间。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func Unix(sec int64, nsec int64) Time

```

这里，“sec”是类型为 int64 的秒，“nsec”是纳秒，也是 int64 类型。

**注意：**允许“nsec”超出范围[0,999999999]是合理的。 但是，并不是每个“秒”值都有相等的时间值，一个类似的值是 1<<63-1，它是最大的 int64 值。

**返回值：**返回相当于从 1970 年 1 月 1 日起以 UTC 表示的 Unix 时间的本地时间。

**示例 1：**

```go
// Golang program to illustrate the usage of
// time.Unix() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Calling Unix method with 275 seconds
    // and zero nanoseconds and also
    // printing output
    fmt.Println(time.Unix(275, 0).UTC())

    // Calling Unix method with 0 seconds and
    // 566 nanoseconds and also printing
    // output
    fmt.Println(time.Unix(0, 566).UTC())

    // Calling Unix method with 456 seconds and
    // -67 nanoseconds and also printing
    // output
    fmt.Println(time.Unix(456, -67).UTC())
}
```

发帖主题：Re：Колибри0.7.8.0

**示例 2：**

```go
// Golang program to illustrate the usage of
// time.Unix() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Calling Unix method with 2e1 seconds
    // and zero nanoseconds and also
    // printing output
    fmt.Println(time.Unix(2e1, 0).UTC())

    // Calling Unix method with 0 seconds and
    // 1e13 nanoseconds and also printing
    // output
    fmt.Println(time.Unix(0, 1e13).UTC())

    // Calling Unix method with 1e1 seconds and
    // -1e15 nanoseconds and also printing
    // output
    fmt.Println(time.Unix(1e1, -1e15).UTC())
}
```

发帖主题：Re：Колибри0.7.8.0

在这里，上面代码中所述的 unix()方法的参数的值包含一个常量“e”，在转换时会在通常的范围内转换该常量。