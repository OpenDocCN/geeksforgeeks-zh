# Golang 中的 time.Date()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-date-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-date-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**date()**函数用于在指定位置的适当时区中查找相当于**yyyy-mm-dd hh：mm：ss+nsec 纳秒**的日期和时间。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func Date(year int, month Month, day, hour, min, sec, nsec int, loc *Location) Time

```

这里，“loc”指的是位置。

**返回值：**它返回一个在转换中的两个关联区域之一中正确的时间，但它不能保证返回哪个区域。 如果给定的“loc”为零，则返回恐慌。

**注意：**此处，月、日、时、分、秒和纳秒的值可以大于正常范围，但在转换过程中它们将自动归一化。 例如，如果日期是 4 月 34，则转换为 5 月 1 日。

**示例 1：**

```go
// Golang program to illustrate the usage of
// time.Date() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Calling Date() method 
    // with all its parameters
    tm := time.Date(2020, time.April,
        11, 21, 34, 01, 0, time.UTC)

    // Using Local() for location and printing
    // the stated time and date in UTC
    fmt.Printf("%s", tm.Local())
}
```

发帖主题：Re：Колибри0.7.8.0

**示例 2：**

```go
// Golang program to illustrate the usage of
// time.Date() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Calling Date() method 
    // with all its parameters
    tm := time.Date(2020, time.April, 
          34, 25, 72, 01, 0, time.UTC)

    // Using Local() for location and printing
    // the stated time and date in UTC
    fmt.Printf("%s", tm.Local())
}
```

发帖主题：Re：Колибри0.7.8.0

在这里，天、小时和分钟的值范围超出了正常范围，但它们在转换过程中被规格化了。