# Golang 中的 time.Time.NanosSecond()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-nanosecond-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-nanosecond-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**time.NanosSecond()**函数用于查找“t”提供的秒内的纳秒偏移量，范围为[0,999999999]。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些功能。

**语法：**

```go
func (t Time) Nanosecond() int

```

这里，“t”是规定的时间。

**返回值：**它返回“t”提供的秒内的纳秒偏移量。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Time.Nanosecond() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring t in UTC
    t := time.Date(2017, 23, 5, 11,
              51, 04, 30, time.UTC)

    // Calling Nanosecond method
    nano := t.Nanosecond()

    // Prints nanoseconds as specified
    fmt.Printf("The stated nanoseconds "+
              "specified is: %v\n", nano)
}
```

发帖主题：Re：Колибри0.7.8.0

**示例 2：**

```go
// Golang program to illustrate the usage of
// Time.Nanosecond() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring t in UTC
    t := time.Date(2017, 34, 56, 78,
      87, 97, 687678678685757, time.UTC)

    // Calling Nanosecond method
    nano := t.Nanosecond()

    // Prints nanoseconds as specified
    fmt.Printf("The stated nanoseconds "+
              "specified is: %v\n", nano)
}
```

发帖主题：Re：Колибри0.7.8.0

在这里，上面代码中声明的纳秒超出了通常的范围，但在转换时会进行标准化。