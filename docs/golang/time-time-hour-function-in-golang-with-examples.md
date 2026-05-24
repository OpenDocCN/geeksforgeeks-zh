# Golang 中的 time.Time.Hour()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-hour-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-hour-function-in-golang-with-examples/)

GO 语言中的**Time.Hour()**函数用于检查所述“t”在范围[0，23]内出现的一天中的小时。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (t Time) Hour() int

```

这里，“t”是规定的时间。

**返回值：**它返回所述“t”出现的一天内的小时数。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Time.Hour() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring t in UTC
    t := time.Date(2020, 5, 36, 
      11, 45, 04, 0, time.UTC)

    // Calling Hour method
    hr := t.Hour()

    // Prints hour as specified
    fmt.Printf("The stated hour "+
      "within the day is: %v\n", hr)
}
```

发帖主题：Re：Колибри0.7.8.0

**示例 2：**

```go
// Golang program to illustrate the usage of
// Time.Hour() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring t in UTC
    t := time.Date(2020, 5, 36,
       29, 45, 04, 0, time.UTC)

    // Calling Hour method
    hr := t.Hour()

    // Prints hour as specified
    fmt.Printf("The stated hour"+
     " within the day is: %v\n", hr)
}
```

发帖主题：Re：Колибри0.7.8.0

在这里，规定的小时超出了通常的范围，但在转换时已标准化。