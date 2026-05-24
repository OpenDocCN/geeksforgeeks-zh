# Golang 中的 time.Time.AddDate()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-adddate-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-adddate-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 Go 语言中的**Time.AddDate()**函数用于检查时间，这相当于将指定的年数、月数和天数与给定的“t”相加。
例如，如果该方法的参数类似于(-2，4，5)，并且声明的 t 为 2018 年 2 月 3 日，则输出将为 2016 年 6 月 8 日。 与这里的日期方法一样，如果月、日或年的范围超出正常范围，则它会自动转换为归一化范围。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些功能。

**语法：**

```go
func (t Time) AddDate(years int, months int, days int) Time

```

这里，“t”是规定的时间。

**返回值：**它返回声明的 t 与声明的年数、月数和天数相加的结果。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Time.AddDate() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring Time in UTC
    Time := time.Date(2018, 6, 4, 0, 0, 0, 0, time.UTC)

    // Calling AddDate method with all
    // its parameters
    t1 := Time.AddDate(1, 2, 5)
    t2 := Time.AddDate(5, -2, 9)
    t3 := Time.AddDate(0, 3, -3)
    t4 := Time.AddDate(1, 0, 0)

    // Prints output
    fmt.Printf("%v\n", Time)
    fmt.Printf("%v\n", t1)
    fmt.Printf("%v\n", t2)
    fmt.Printf("%v\n", t3)
    fmt.Printf("%v\n", t4)
}
```

发帖主题：Re：Колибри0.7.0

```go
2018-06-04 00:00:00 +0000 UTC
2019-08-09 00:00:00 +0000 UTC
2023-04-13 00:00:00 +0000 UTC
2018-09-01 00:00:00 +0000 UTC
2019-06-04 00:00:00 +0000 UTC

```

这里，返回的输出采用上面定义的 UTC 格式。

**示例 2：**

```go
// Golang program to illustrate the usage of
// Time.AddDate() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring Time in UTC
    Time := time.Date(2020, 15, 34, 0, 0, 0, 0, time.UTC)

    // Calling AddDate method with all
    // its parameters
    t1 := Time.AddDate(3, 13, 35)
    t2 := Time.AddDate(2, -24, 29)
    t3 := Time.AddDate(4, 32, -31)
    t4 := Time.AddDate(5, 10, -11)

    // Prints output
    fmt.Printf("%v\n", Time)
    fmt.Printf("%v\n", t1)
    fmt.Printf("%v\n", t2)
    fmt.Printf("%v\n", t3)
    fmt.Printf("%v\n", t4)
}
```

发帖主题：Re：Колибри0.7.0

```go
2021-04-03 00:00:00 +0000 UTC
2025-06-07 00:00:00 +0000 UTC
2021-05-02 00:00:00 +0000 UTC
2027-11-02 00:00:00 +0000 UTC
2027-01-23 00:00:00 +0000 UTC

```

在这里，使用的范围超出了通常的范围，但它们在转换时会被规格化。