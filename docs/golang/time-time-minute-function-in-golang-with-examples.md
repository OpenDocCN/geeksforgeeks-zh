# Golang 中的 time.Time.Minant()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-minute-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-minute-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**Time.Minant()**函数用于查找由“t”提供的规定小时内的分钟偏移量，范围为[0，59]。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (t Time) Minute() int

```

这里，“t”是规定的时间。

**返回值：**它返回“t”提供的规定小时内的分钟偏移量。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Time.Minute() function

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

    // Calling Minute method
    min := t.Minute()

    // Prints minute as specified
    fmt.Printf("The stated minute within"+
     " the hour specified is: %v\n", min)
}
```

发帖主题：Re：Колибри0.7.8.0

**示例 2：**

```go
// Golang program to illustrate the usage of
// Time.Minute() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring t in UTC
    t := time.Date(2019, 6, 5,
       11, 91, 04, 0, time.UTC)

    // Calling Minute method
    min := t.Minute()

    // Prints minute as specified
    fmt.Printf("The stated minute within"+
       " the hour specified is: %v\n", min)
}
```

发帖主题：Re：Колибри0.7.8.0

在这里，声明的分钟超出了通常的范围，但它在转换时是标准化的。