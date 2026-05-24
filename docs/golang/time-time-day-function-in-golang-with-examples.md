# Golang 中的 time.Time.Day()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-day-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-day-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**Time.Day()**函数用于检查指定的“t”出现在哪个月的哪一天。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (t Time) Day() int

```

这里，“t”是规定的时间。

**返回值：**它返回所述“t”出现的月份的第几天。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Time.Day() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring t in UTC
    t := time.Date(2020, 5, 6, 11, 45, 04, 0, time.UTC)

    // Calling Day method
    dd := t.Day()

    // Prints day
    fmt.Printf("The stated day is: %v\n", dd)
}
```

发帖主题：Re：Колибри0.7.8.0

**示例 2：**

```go
// Golang program to illustrate the usage of
// Time.Day() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring t in UTC
    t := time.Date(2020, 5, 36, 11, 45, 04, 0, time.UTC)

    // Calling Day method
    dd := t.Day()

    // Prints day
    fmt.Printf("The stated day is: %v\n", dd)
}
```

发帖主题：Re：Колибри0.7.8.0

在这里，声明的日期超出了通常的范围，但它在转换时被标准化。