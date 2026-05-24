# Golang 中的 time.Truncate()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-truncate-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-truncate-function-in-golang-with-examples/)

在围棋语言中，时间包提供了确定和查看时间的功能。 GO 语言中的**Truncate()函数**用于找出将所述持续时间‘d’舍入为‘m’持续时间的倍数的结果。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (d Duration) Truncate(m Duration) Duration

```

这里，d 是四舍五入的持续时间，m 是倍数。

**返回值：**它返回将声明的持续时间‘d’四舍五入为‘m’持续时间的倍数的结果。 但如果 m 小于或等于零，则返回未更改的‘d’。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Truncate() function

// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Calling main
func main() {

    // Defining duration
    // of Truncate method
    tr, _ := time.ParseDuration("45m32.67s")

    // Prints truncated duration
    fmt.Printf("Truncated duration is : %s", 
                 tr.Truncate(2*time.Second))
}
```

发帖主题：Re：Колибри0.7.8.0

在这里，‘d’四舍五入为 m 的倍数。

**示例 2：**

```go
// Golang program to illustrate the usage of
// Truncate() function

// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Calling main
func main() {

    // Defining duration of Truncate method
    tr, _ := time.ParseDuration("7m11.0530776s")

    // Array of m
    t := []time.Duration{
        time.Microsecond,
        time.Second,
        4 * time.Second,
        11 * time.Minute,
    }

    // Using for loop and range to
    // iterate over an array
    for _, m := range t {

        // Prints rounded d of all 
        // the items in an array
        fmt.Printf("Truncated(%s) is : %s\n",
                           m, tr.Truncate(m))
    }
}
```

发帖主题：Re：Колибри0.7.8.0

这里，首先形成一个‘t’数组，然后使用一个范围来迭代持续时间‘t’的所有值。 最后，使用 truncate()方法打印上述代码中 t 的所有四舍五入的值。