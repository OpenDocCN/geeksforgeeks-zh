# Golang 中的 time.Time.YearDay()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-yearday-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-yearday-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**Time.YearDay()**函数用于查找“t”提供的日期。 其中，非闰年的范围是[1,365]，闰年的范围是[1,366]。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

> **语法：**
> 
> ```go
> func (t Time) YearDay() int
> 
> ```
> 
> 这里，“t”是规定的时间。
> 
> **返回值：**返回“t”指定的一年中的第几天。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Time.YearDay() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring t in UTC
    t := time.Date(2019, 6, 5, 11,
              35, 04, 0, time.UTC)

    // Calling YearDay method
    yrday := t.YearDay()

    // Prints the day 
    // of the year as specified
    fmt.Printf("The day of the year "+
      "in the 't' specified is: %v\n", yrday)
}
```

发帖主题：Re：Колибри0.7.8.0

**示例 2：**

```go
// Golang program to illustrate the usage of
// Time.YearDay() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring t in UTC
    t := time.Date(2020, 35, 60, 
       45, 67, 94, 7567, time.UTC)

    // Calling YearDay method
    yrday := t.YearDay()

    // Prints the day of the year as specified
    fmt.Printf("The day of the year in "+
      "the 't' specified is: %v\n", yrday)
}
```

发帖主题：Re：Колибри0.7.8.0

在这里，上面提到的“t”的值超出了通常的范围，但它们在转换时被标准化了。