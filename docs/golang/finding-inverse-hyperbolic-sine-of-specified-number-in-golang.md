# 求 Golang 中指定数的反双曲正弦

> 原文:[https://www . geeksforgeeks . org/finding-inverse-双曲线-正弦-指定数字 in-golang/](https://www.geeksforgeeks.org/finding-inverse-hyperbolic-sine-of-specified-number-in-golang/)

Go 语言在**数学包**的帮助下，为基本常数和数学函数提供了对数字进行运算的内置支持。您可以借助数学包提供的 **Asinh()函数**找到指定数字的反双曲正弦。因此，您需要在导入关键字的帮助下在程序中添加一个数学包来访问 Asinh()函数。

**语法:**

```go
func Asinh(y float64) float64
```

*   如果在这个函数中传递+Inf 或-Inf，那么这个函数将返回+Inf 或-Inf。
*   如果在这个函数中传递 NaN，那么这个函数将返回 NaN。
*   如果在此函数中传递 0，则此函数将返回 0。

**例 1:**

```go
// Golang program to illustrate how to find
// the inverse hyperbolic sine of the
// given number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding the inverse hyperbolic
    // sine of the given value
    // Using Asinh() function
    res_1 := math.Asinh(math.Pi / 2)
    res_2 := math.Asinh(math.Inf(-3))
    res_3 := math.Asinh(0)
    res_4 := math.Asinh(math.NaN())
    res_5 := math.Asinh(1)

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
Result 1: 1.2
Result 2: -Inf
Result 3: 0.0
Result 4: NaN
Result 5: 0.9

```

**例 2:**

```go
// Golang program to illustrate how to find
// the inverse hyperbolic sine of the
// given number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding inverse hyperbolic
    // sine of the given number
    nvalue_1 := math.Asinh(math.Pi / 4)
    nvalue_2 := math.Asinh(math.Pi / 6)

    // Sum of the given values
    res := nvalue_1 + nvalue_2

    // Displaying results
    fmt.Printf("%.1f + %.1f = %.1f", 
            nvalue_1, nvalue_2, res)

}
```

**输出:**

```go
0.7 + 0.5 = 1.2
```