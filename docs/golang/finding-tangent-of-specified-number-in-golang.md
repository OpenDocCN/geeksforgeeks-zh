# 求 Golang 中指定数的正切值

> 原文:[https://www . geeksforgeeks . org/finding-指定数字的切线 in-golang/](https://www.geeksforgeeks.org/finding-tangent-of-specified-number-in-golang/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。您可以借助**数学包**提供的 **Tan()函数**找到指定弧度参数的正切值。因此，您需要在程序中添加一个数学包，借助 import 关键字来访问 Tan()函数。

**语法:**

```go
func Tan(y float64) float64
```

*   如果在这个函数中传递+Inf 或-Inf，那么这个函数将返回 NaN(不是数字)。
*   如果在这个函数中传递 NaN，那么这个函数将返回 NaN。
*   如果在此函数中传递 0，则此函数将返回 0。

**例 1:**

```go
// Golang program to illustrate how to find
// the tangent of the given radian argument

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding the tangent
    // of the given value
    // Using Tan() function
    res_1 := math.Tan(math.Pi / 4)
    res_2 := math.Tan(math.Inf(-3))
    res_3 := math.Tan(0)
    res_4 := math.Tan(math.NaN())
    res_5 := math.Tan(math.Pi)

    // Displaying the result
    fmt.Printf("Result 1: %.1f", res_1)
    fmt.Printf("\nResult 2: %.1f", res_2)
    fmt.Printf("\nResult 3: %.1f", res_3)
    fmt.Printf("\nResult 4: %.1f", res_4)
    fmt.Printf("\nResult 5: %.1f", res_5)
}
```

**输出:**

```go
Result 1: 1.0
Result 2: NaN
Result 3: 0.0
Result 4: NaN
Result 5: -0.0

```

**例 2:**

```go
// Golang program to illustrate how to find
// the tangent of the given radian argument

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding tangent 
    // of the given number
    nvalue_1 := math.Tan(math.Pi / 3)
    nvalue_2 := math.Tan(math.Pi / 6)

    // Sum of the given values
    res := nvalue_1 + nvalue_2

    // Displaying results
    fmt.Printf("%.1f + %.1f = %.1f", 
            nvalue_1, nvalue_2, res)

}
```

**输出:**

```go
1.7 + 0.6 = 2.3
```