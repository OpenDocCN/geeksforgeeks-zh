# 在 Golang 中求指定数的立方根

> 原文:[https://www . geeksforgeeks . org/find-cube-root-of-specific-number-in-golang/](https://www.geeksforgeeks.org/finding-cube-root-of-specified-number-in-golang/)

Go 语言在**数学包**的帮助下，为基本常数和数学函数提供了对数字进行运算的内置支持。您可以借助数学包提供的**Cbort()函数**找到指定数字的立方根。因此，您需要在程序中添加一个数学包，借助 import 关键字来访问 Cbrt()函数。

**语法:**

```go
func Cbrt(y float64) float64
```

*   如果在这个函数中传递+Inf 或-Inf，那么这个函数将返回+Inf 或-Inf。
*   如果在此函数中传递 0，则此函数将返回 0。
*   如果在这个函数中传递 NaN(不是数字)，那么这个函数将返回 NaN。

**例 1:**

```go
// Golang program to illustrate how to find
// the cube root of the given number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding the cube root
    // of the given value
    // Using Cbrt() function
    res_1 := math.Cbrt(3)
    res_2 := math.Cbrt(math.Inf(-3))
    res_3 := math.Cbrt(0)
    res_4 := math.Cbrt(math.NaN())

    // Displaying the result
    fmt.Printf("Result 1: %.1f", res_1)
    fmt.Printf("\nResult 2: %.1f", res_2)
    fmt.Printf("\nResult 3: %.1f", res_3)
    fmt.Printf("\nResult 4: %.1f", res_4)
}
```

**输出:**

```go
Result 1: 1.4
Result 2: -Inf
Result 3: 0.0
Result 4: NaN

```

**例 2:**

```go
// Golang program to illustrate how to find
// the cube root of the given number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding cube root 
    // of the given number
    nvalue_1 := math.Cbrt(3)
    nvalue_2 := math.Cbrt(-7)

    // Sum of the given values
    res := nvalue_1 + nvalue_2

    // Displaying results
    fmt.Printf("%.1f + %.1f = %.1f",
            nvalue_1, nvalue_2, res)

}
```

**输出:**

```go
1.4 + -1.9 = -0.5
```