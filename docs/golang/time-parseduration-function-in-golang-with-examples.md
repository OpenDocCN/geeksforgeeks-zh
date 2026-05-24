# Golang 中的 time.ParseDuration()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-parseduration-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-parseduration-function-in-golang-with-examples/)

Go 语言在**时间包**的帮助下为测量和显示时间提供内置支持。 在此软件包中，日历计算始终假定公历没有闰秒。 此包提供了**ParseDuration()函数**，用于解析持续时间字符串。 持续时间字符串是带有可选分数和单位后缀的有符号十进制数字序列，如“100ms”、“2.3h”或“4h35m”。 要访问 ParseDuration()函数，您需要在程序中借助 import 关键字添加一个时间包。

**注意：**有效时间单位为“ns”、“us”(或“µs”)、“ms”、“s”、“m”、“h”。

**语法：**

```go
func ParseDuration(str string) (Duration, error)
```

**示例 1：**

```go
// Golang program to illustrate
// how to find time duration
package main

import (
    "fmt"
    "time"
)

func main() {

    // Using ParseDuration() function
    hr, _ := time.ParseDuration("3h")
    comp, _ := time.ParseDuration("5h30m40s")

    fmt.Println("Time Duration 1: ", hr)
    fmt.Println("Time Duration 2: ", comp)

}
```

发帖主题：Re：Колибри0.7.0

```go
Time Duration 1:  3h0m0s
Time Duration 2:  5h30m40s

```

**示例 2：**

```go
// Golang program to illustrate
// how to find time duration
package main

import (
    "fmt"
    "time"
)

func main() {

    // Using ParseDuration() function
    hr, _ := time.ParseDuration("5h")
    comp, _ := time.ParseDuration("2h30m40s")
    m1, _ := time.ParseDuration("3µs")
    m2, _ := time.ParseDuration("3us")

    fmt.Println("Time Duration 1: ", hr)
    fmt.Println("Time Duration 2: ", comp)
    fmt.Printf("There are %.0f seconds in %v.\n",
                            comp.Seconds(), comp)

    fmt.Printf("There are %d nanoseconds in %v.\n",
                              m1.Nanoseconds(), m1)

    fmt.Printf("There are %6.2e seconds in %v.\n",
                                 m2.Seconds(), m1)
}
```

发帖主题：Re：Колибри0.7.0

```go
Time Duration 1:  5h0m0s
Time Duration 2:  2h30m40s
There are 9040 seconds in 2h30m40s.
There are 3000 nanoseconds in 3µs.
There are 3.00e-06 seconds in 3µs.

```