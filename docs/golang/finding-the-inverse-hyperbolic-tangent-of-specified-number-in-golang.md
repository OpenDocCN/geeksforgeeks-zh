# 求 Golang 中指定数的反双曲正切值

> 原文:[https://www . geeksforgeeks . org/find-the-reverse-双曲线-正切-指定数-in-golang/](https://www.geeksforgeeks.org/finding-the-inverse-hyperbolic-tangent-of-specified-number-in-golang/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。借助**数学包**提供的 **Atanh()函数**，可以求出指定数的反双曲正切。因此，您需要在导入关键字的帮助下在程序中添加一个数学包来访问 Atanh()函数。

**语法:**

```go
func Atanh(y float64) float64
```

*   如果在这个函数中传递 1，那么这个函数将返回+Inf。
*   如果在这个函数中传递-1，那么这个函数将返回-Inf。
*   如果在此函数中传递-0 或+0，则此函数将返回-0 或+0。
*   如果在这个函数中传递 NaN，那么这个函数将返回 NaN。
*   如果 y < -1 or y > 1，那么这个函数将返回 NaN。

**例 1:**

```go
// Golang program to illustrate how to find the
// inverse hyperbolic tangent of the given number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding the inverse hyperbolic
    // tangent of the given value
    // Using Atanh() function
    res_1 := math.Atanh(math.Pi / 4)
    res_2 := math.Atanh(math.Inf(-3))
    res_3 := math.Atanh(0)
    res_4 := math.Atanh(math.NaN())
    res_5 := math.Atanh(-1)

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
Result 1: 1.1
Result 2: NaN
Result 3: 0.0
Result 4: NaN
Result 5: -Inf

```

**例 2:**

```go
// Golang program to illustrate how to find the
// inverse hyperbolic tangent of the given number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding inverse hyperbolic 
    // tangent of the given number
    nvalue_1 := math.Atanh(math.Pi / 3)
    nvalue_2 := math.Atanh(math.Pi / 6)

    // Sum of the given values
    res := nvalue_1 + nvalue_2

    // Displaying results
    fmt.Printf("%.1f + %.1f = %.1f", 
            nvalue_1, nvalue_2, res)

}
```

**输出:**

```go
NaN + 0.6 = NaN
```