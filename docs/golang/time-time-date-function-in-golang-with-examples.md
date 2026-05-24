# Golang 中的 time.Time.Date()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-date-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-date-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 Go 语言中的**Time.Date()**函数用于检查所述“t”出现的年、月和日。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (t Time) Date() (year int, month Month, day int)

```

这里，“t”是规定的时间。

**返回值：**返回所述 t 的年、月、日。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Time.Before() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring t in UTC
    t := time.Date(2020, 5, 6, 11, 45, 04, 0, time.UTC)

    // Calling Date method
    yyyy, mm, dd := t.Date()

    // Prints year
    fmt.Printf("The stated year is: %v\n", yyyy)

    // Prints month
    fmt.Printf("The stated month is: %v\n", mm)

    // Prints day
    fmt.Printf("The stated day is: %v\n", dd)
}
```

发帖主题：Re：Колибри0.7.8.0

**示例 2：**

```go
// Golang program to illustrate the usage of
// Time.Before() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring t in UTC
    t := time.Date(2020, 13, 34, 00, 00, 00, 0, time.UTC)

    // Calling Date method
    yyyy, mm, dd := t.Date()

    // Prints year
    fmt.Printf("The stated year is: %v\n", yyyy)

    // Prints month
    fmt.Printf("The stated month is: %v\n", mm)

    // Prints day
    fmt.Printf("The stated day is: %v\n", dd)
}
```

发帖主题：Re：Колибри0.7.8.0

在这里，声明的月和日超出了通常的范围，但它们在转换时是标准化的。