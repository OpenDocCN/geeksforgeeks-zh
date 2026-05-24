# Golang 中的 time.Time.UTC()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-utc-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-utc-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**Time.UTC()**函数用于生成位置设置为 UTC 的“t”。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (t Time) UTC() Time

```

这里，“t”是以 UTC 表示的时间。

**返回值：**它返回 t，位置设置为 UTC。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Time.UTC() function

// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Calling main
func main() {

    // Defining t for UTC method
    t := time.Date(2020, 11, 14, 11, 30, 32, 0, time.UTC)

    // Calling UTC method
    utc := t.UTC()

    // Prints output
    fmt.Printf("%v\n", utc)
}
```

发帖主题：Re：Колибри0.7.8.0

**示例 2：**

```go
// Golang program to illustrate the usage of
// Time.UTC() function

// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Calling main
func main() {

    // Defining t for UTC method
    t := time.Date(2020, 23, 40, 56, 70, 0, 0, time.UTC)

    // Calling UTC method
    utc := t.UTC()

    // Prints output
    fmt.Printf("%v\n", utc)
}
```

发帖主题：Re：Колибри0.7.8.0

在这里，上面代码中声明的时间“t”的值超出了通常的范围，但它们在转换时被标准化了。