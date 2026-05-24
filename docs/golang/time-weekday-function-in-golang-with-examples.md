# Golang 中的 time.Weekday()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-weekday-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-weekday-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**Weekday()**函数用于检查日期的英文名称。 此外，该函数在**时间包**下定义。 在这里，您需要导入“time”包才能使用这些功能。

**语法：**

```go
func (d Weekday) String() string

```

**返回值：**返回当天的英文名称。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Weekday() function

// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Main function
func main() {

    // Calling Weekday method using
    // Now function
    weekday := time.Now().Weekday()

    // Prints the current weekday
    fmt.Println("Weekday is: ", weekday)
}
```

发帖主题：Re：Колибри0.7.0

```go
Weekday is:  Thursday

```

**示例 2：**

```go
// Golang program to illustrate the usage of
// Weekday() function

// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Main function
func main() {

    // Calling Weekday method using
    // Now function
    weekday := time.Now().Weekday()

    // Prints the current 
    // weekday in int form
    fmt.Println("Weekday in number is: ", int(weekday))
}
```

发帖主题：Re：Колибри0.7.0

```go
Weekday in number is:  4

```