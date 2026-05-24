# Golang 中的 time.Time.Clock()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-clock-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-clock-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**Time.Clock()**函数用于检查所述“t”出现的日期内的小时、分钟和秒。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (t Time) Clock() (hour, min, sec int)

```

这里，“t”是规定的时间。

**返回值：**返回所述 t 的时、分、秒。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Time.Clock() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring t in UTC
    t := time.Date(2020, 13, 34, 12, 45, 55, 0, time.UTC)

    // Calling Clock method
    hour, minute, second := t.Clock()

    // Prints hours
    fmt.Printf("The stated hour is: %v hours\n", hour)

    // Prints minutes
    fmt.Printf("The stated minute is: %v minutes\n", minute)

    // Prints seconds
    fmt.Printf("The stated second is: %v seconds\n", second)
}
```

发帖主题：Re：Колибри0.7.8.0

**示例 2：**

```go
// Golang program to illustrate the usage of
// Time.Clock() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring t in UTC
    t := time.Date(2020, 13, 34, 25, 66, 100, 0, time.UTC)

    // Calling Clock method
    hour, minute, second := t.Clock()

    // Prints hours
    fmt.Printf("The stated hour is: %v hours\n", hour)

    // Prints minutes
    fmt.Printf("The stated minute is: %v minutes\n", minute)

    // Prints seconds
    fmt.Printf("The stated second is: %v seconds\n", second)
}
```

发帖主题：Re：Колибри0.7.8.0

在这里，声明的小时、分钟和天超出了通常的范围，但它们在转换时是标准化的。