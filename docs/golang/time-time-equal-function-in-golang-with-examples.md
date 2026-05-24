# Golang 中的 time.Time.equence()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-equal-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-equal-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 围棋语言中的**Time.Eque.**函数用于检查所述时间“t”和“u”是否表示相同的时间瞬间。 而位于不同位置的两次甚至可以相等。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (t Time) Equal(u Time) bool

```

这里，“t”和“u”是规定的时间。

**返回值：**如果所述时间相等，则返回 TRUE，否则返回 FALSE。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Time.Equal() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Defining t and u parameter of Equal method
    t := time.Date(2020, 3, 2, 12, 14, 0, 0, time.UTC)
    u := time.Date(2020, 3, 1, 36, 14, 0, 0, time.UTC)

    // Calling Equal method
    TimesequalOrnot := t.Equal(u)

    // Prints output
    fmt.Printf("%v\n", TimesequalOrnot)
}
```

发帖主题：Re：Колибри0.7.0

```go
true

```

**示例 2：**

```go
// Golang program to illustrate the usage of
// Time.Equal() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Defining t and u parameter 
    // of Equal method
    t := time.Date(2020, 3, 2, 12, 
              14, 07, 0, time.UTC)

    u := time.Date(2020, 3, 1, 36,
               14, 0, 0, time.UTC)

    // Calling Equal method
    TimesequalOrnot := t.Equal(u)

    // Prints output
    fmt.Printf("%v\n", TimesequalOrnot)
}
```

发帖主题：Re：Колибри0.7.0

```go
false

```