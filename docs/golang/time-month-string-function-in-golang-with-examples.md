# Golang 中的 time.Month.String()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-month-string-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-month-string-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 Go 语言中的**Month.String()**函数用于查找月份的英文名称。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (m Month) String() string

```

这里，“m”是类型月份。

**返回值：**它返回一个字符串，该字符串是月份的英文名称。

**示例 1：**

```go
// Golang program to illustrate the usage of
// (Month) String() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Calling time.Month
    // with its parameter
    // of type int
    var m = time.Month(2)

    // Prints the English 
    // name of the month
    fmt.Println(m.String())
}
```

发帖主题：Re：Колибри0.7.0

```go
February

```

**示例 2：**

```go
// Golang program to illustrate the usage of
// (Month) String() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Calling time.Month
    // with its parameter
    // of type int
    var m = time.Month(12)

    // Prints the English name of 
    // the month
    fmt.Println(m.String())
}
```

发帖主题：Re：Колибри0.7.0

```go
December

```