# Golang 中的

# time.String()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-string-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-string-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**string()**函数用于查找将持续时间格式表示为“24h6m0.7s”的字符串。 在这里，最前面的零单位被删除。 并且规定的少于一秒格式的持续时间将使用较小的单位，例如毫秒、微秒或纳秒，以确保最前面的数字不是零。 持续时间 0 的格式为 0。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (d Duration) String() string

```

这里，d 是持续时间。

**返回值：**它返回将持续时间格式表示为 3h4m0.3s 的字符串。

**示例 1：**

```go
// Golang program to illustrate the usage of
// time.String() function

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
    // of String method
    str, _ := time.ParseDuration("3h")

    // Prints string that
    // represents duration
    fmt.Printf(str.String())
}
```

发帖主题：Re：Колибри0.7.8.0

**示例 2：**

```go
// Golang program to illustrate the usage of
// time.String() function

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
    // of String method
    time1 := time.Date(2019, time.October, 
                 23, 0, 0, 0, 0, time.UTC)

    time2 := time.Date(2020, time.April,
                3, 0, 0, 0, 0, time.UTC)

    // Prints the duration of time stated
    fmt.Println(time2.Sub(time1).String())
}
```

发帖主题：Re：Колибри0.7.8.0

这里，Time1 和 Time2 之间的时长以字符串的形式返回。