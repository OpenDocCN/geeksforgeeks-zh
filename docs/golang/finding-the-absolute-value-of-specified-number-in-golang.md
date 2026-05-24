# 求 Golang 中指定数的绝对值

> 原文:[https://www . geesforgeks . org/find-指定数字的绝对值 in-golang/](https://www.geeksforgeeks.org/finding-the-absolute-value-of-specified-number-in-golang/)

Go 语言在**数学包**的帮助下，为基本常数和数学函数提供了对数字进行运算的内置支持。您可以借助数学包提供的 **Abs()函数**找到指定数字的绝对值。因此，您需要在导入关键字的帮助下在程序中添加一个数学包来访问 Abs()函数。

*   如果在这个函数中传递无穷大(Inf)，那么这个函数将返回+Inf
*   如果在这个函数中传递 NaN(不是数字)，那么这个函数将返回 NaN。

**语法:**

```go
func Abs(y float64) float64
```

让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Golang program to illustrate
// how to find absolute value
package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding absolute value
    // Using Abs() function
    res_1 := math.Abs(4)
    res_2 := math.Abs(-8)
    res_3 := math.Abs(math.Inf(-3))

    // Displaying the result
    fmt.Printf("Result 1: %.1f", res_1)
    fmt.Printf("\nResult 2: %.1f", res_2)
    fmt.Printf("\nResult 3: %.1f", res_3)
}
```

**输出:**

```go
Result 1: 4.0
Result 2: 8.0
Result 3: +Inf

```

**例 2:**

```go
// Golang program to illustrate
// how to find absolute value
package main

import (
    "fmt"
    "math"
)

// Main function
func main() {
    // Finding absolute value
    nvalue_1 := math.Abs(20)
    nvalue_2 := math.Abs(34)

    // Sum of the given values
    res := nvalue_1 + nvalue_2

    // Displaying results
    fmt.Printf("%.1f + %.1f = %.1f",
            nvalue_1, nvalue_2, res)

}
```

**输出:**

```go
20.0 + 34.0 = 54.0
```