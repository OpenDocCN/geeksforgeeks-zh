# Golang 中的 time.round()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-round-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-round-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 围棋语言中的**round()**函数用于查找将所述持续时间‘d’四舍五入为‘m’持续时间的最接近倍数的结果。 这里，中间值的舍入方式是从 0 开始舍入。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (d Duration) Round(m Duration) Duration

```

这里，d 是要舍入的持续时间，m 是最接近的倍数。

**返回值：**如果结果超过了在持续时间内可以存储的最大(或最小)值，则返回最大(或最小)持续时间。 但如果 m 小于或等于 0，则返回未更改的‘d’。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Round() function

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
    // of Round method
    d, _ := time.ParseDuration("5m7s")

    // Prints rounded d
    fmt.Printf("Rounded d is : %s", 
            d.Round(6*time.Second))
}
```

发帖主题：Re：Колибри0.7.8.0

这里，‘d’四舍五入为 m 的最接近倍数。

**示例 2：**

```go
// Golang program to illustrate the usage of
// Round() function

// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Calling main
func main() {

    // Defining duration of Round method
    d, _ := time.ParseDuration("3m73.671s")

    // Array of m
    R := []time.Duration{
        time.Microsecond,
        time.Second,
        3 * time.Second,
        9 * time.Minute,
    }

    // Using for loop and range to
    // iterate over an array
    for _, m := range R {

        // Prints rounded d of all 
        // the items in an array
        fmt.Printf("Rounded(%s) is : %s\n", 
                             m, d.Round(m))
    }
}
```

发帖主题：Re：Колибри0.7.8.0

这里，首先形成‘d’数组，然后使用范围迭代 d 的所有值，最后使用 round()方法打印 d 的所有四舍五入的值。