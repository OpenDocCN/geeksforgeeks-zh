# Golang 中的 time.Time.Truncate()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-truncate-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-truncate-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**Time.Truncate()**函数用于查找将指定时间“t”四舍五入为给定持续时间“d”从零开始的最接近倍数的输出。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (t Time) Truncate(d Duration) Time

```

这里，“t”是规定的时间，“d”是给定的持续时间。

**注意：**truncate()方法在时间上以从零开始的绝对持续时间的形式工作。 然而，它在当时的布局形式上不起作用。

**返回值：**它返回将给定时间“t”四舍五入为所述持续时间“d”的最接近倍数的输出。 其中，如果 d 小于或等于零，则它从任何单调时钟读数中返回“t”，否则不变。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Time.Truncate() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Defining t for Truncate method
    t := time.Date(2007, 7, 6, 23, 58, 11, 60, time.UTC)

    // Defining duration
    d := (60 * time.Second)

    // Calling Truncate() method
    trunc := t.Truncate(d)

    // Prints output
    fmt.Printf("The result after rounding 't' is: %v\n", trunc)
}
```

发帖主题：Re：Колибри0.7.8.0

**示例 2：**

```go
// Golang program to illustrate the usage of
// Time.Truncate() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Defining t for Truncate method
    t := time.Date(2047, 47, 96, 123, 98, 81, 999434, time.UTC)

    // Defining duration
    d := (2 * time.Hour)

    // Calling Truncate() method
    trunc := t.Truncate(d)

    // Prints output
    fmt.Printf("The result after rounding 't' is: %v\n", trunc)
}
```

发帖主题：Re：Колибри0.7.8.0

在这里，上面代码中声明的“t”具有超出通常范围的值，但它们在转换时被标准化。