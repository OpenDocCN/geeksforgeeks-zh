# Golang 中的 time.Time.In()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-in-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-in-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**in()**函数用于查找所述“t”的副本，该副本表示相同的时间瞬间，但该副本的位置数据被设置为“loc”以供显示使用。 如果“loc”为零，则返回恐慌。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (t Time) In(loc *Location) Time

```

这里，“t”是指定的时间，“loc”是指定的位置，它是指向该位置的指针。

**返回值：**它返回所述“t”的副本，该副本表示相同的时刻，但同时返回副本的位置数据，该副本的位置数据被设置为“loc”以供显示使用。 如果“loc”为零，则返回恐慌。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Time.In() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Defining t for In method
    t := time.Date(2019, 12, 13, 3, 23, 43, 02, time.UTC)

    // Defining loc parameter of In method
    loc := time.FixedZone("UTC", 6*54*44)

    // Calling In() method
    res := t.In(loc)

    // Prints output
    fmt.Printf("%v\n", res)
}
```

发帖主题：Re：Колибри0.7.8.0

**示例 2：**

```go
// Golang program to illustrate the usage of
// Time.In() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Defining t for In method
    t := time.Date(2022, 23, 45, 36, 67, 88, 667, time.UTC)

    // Defining loc parameter of In method
    loc := time.FixedZone("UTC-6", -3*66*77)

    // Calling In() method
    res := t.In(loc)

    // Prints output
    fmt.Printf("%v\n", res)
}
```

发帖主题：Re：Колибри0.7.8.0

在这里，上面代码中声明的“t”具有超出通常范围的值，但它们在转换时被标准化。