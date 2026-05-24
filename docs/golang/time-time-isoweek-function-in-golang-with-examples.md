# Golang 中的 time.Time.ISOWeek()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-isoweek-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-isoweek-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**ISOWeek()**函数用于查找出现所述“t”的 ISO 8601 年号和周号。 其中一周的范围是从 1 到 53。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (t Time) ISOWeek() (year, week int)

```

这里，“t”是指定的时间，“Year”和“Week”是在此方法中作为输出返回的两个值。

**注：**任何一年的 1 月 1 日至 1 月 3 日说‘n’很可能属于‘n-1’年的第 52 或 53 周，12 月 29 日至 12 月 31 日可能是‘n+1’年的第 1 周的一部分。

**返回值：**返回出现“t”的 ISO 8601 年份和周数。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Time.ISOWeek() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Defining t for ISOWeek method
    t := time.Date(2013, 4, 11, 12, 37, 33, 0, time.UTC)

    // Calling ISOWeek() method
    year, week := t.ISOWeek()

    // Prints the year
    fmt.Printf("year: %v\n", year)

    // Prints the week number
    fmt.Printf("week: %d\n", week)
}
```

发帖主题：Re：Колибри0.7.8.0

**示例 2：**

```go
// Golang program to illustrate the usage of
// Time.ISOWeek() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Defining t for ISOWeek method
    t := time.Date(2022, 35, 37, 29, 99, 70, 6388, time.UTC)

    // Calling ISOWeek() method
    year, week := t.ISOWeek()

    // Prints the year
    fmt.Printf("year: %v\n", year)

    // Prints the week number
    fmt.Printf("week: %d\n", week)
}
```

发帖主题：Re：Колибри0.7.8.0

在这里，上面代码中声明的“t”具有超出通常范围的值，但它们在转换时被标准化。