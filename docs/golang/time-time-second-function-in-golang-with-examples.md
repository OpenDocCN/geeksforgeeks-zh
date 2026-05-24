# Golang 中的 time.Time.Second()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-second-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-second-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**Time.Second()**函数用于查找“t”提供的分钟内的第二个偏移量，范围为[0，59]。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (t Time) Second() int

```

这里，“t”是规定的时间。

**返回值：**返回“t”提供的分钟内的第二个偏移量。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Time.Second() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring t in UTC
    t := time.Date(2017, 2, 3, 13, 
             12, 34, 50, time.UTC)

    // Calling Second method
    sec := t.Second()

    // Prints second as specified
    fmt.Printf("The stated second is: %v\n", sec)
}
```

发帖主题：Re：Колибри0.7.8.0

**示例 2：**

```go
// Golang program to illustrate the usage of
// Time.Second() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring t in UTC
    t := time.Date(2017, 2, 3, 13,
             12, 67, 50, time.UTC)

    // Calling Second method
    sec := t.Second()

    // Prints second as specified
    fmt.Printf("The stated second is: %v\n", sec)
}
```

发帖主题：Re：Колибри0.7.8.0

在这里，上面代码中声明的秒数超出了通常的范围，但在转换时会进行标准化。