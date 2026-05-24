# 求 Golang 中给定数的误差函数

> 原文:[https://www . geeksforgeeks . org/find-error-function-of-given-number-in-golang/](https://www.geeksforgeeks.org/finding-error-function-of-given-number-in-golang/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。您可以借助**数学包**提供的 **Erf()函数**找到指定数字的误差函数。因此，您需要借助 import 关键字在程序中添加一个数学包来访问 Erf()函数。

**语法:**

```go
func Erf(a float64) float64
```

*   如果在这个函数中传递+Inf，那么这个函数将返回 1。
*   如果在这个函数中传递-Inf，那么这个函数将返回-1。
*   如果在这个函数中传递 NaN，那么这个函数将返回 NaN。

**例 1:**

```go
// Golang program to illustrate how to find the
// error function of the given number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding error function
    // Using Erf() function
    res_1 := math.Erf(0.958)
    res_2 := math.Erf(math.Inf(-3))
    res_3 := math.Erf(math.Inf(3))
    res_4 := math.Erf(math.NaN())

    // Displaying the result
    fmt.Printf("Result 1: %.1f", res_1)
    fmt.Printf("\nResult 2: %.1f", res_2)
    fmt.Printf("\nResult 3: %.1f", res_3)
    fmt.Printf("\nResult 4: %.1f", res_4)

}
```

**输出:**

```go
Result 1: 0.8
Result 2: -1.0
Result 3: 1.0
Result 4: NaN

```

**例 2:**

```go
// Golang program to illustrate how to find the
// error function of the given number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding error function
    // Using Erf() function
    nvalue_1 := math.Erf(0.8457)
    nvalue_2 := math.Erf(4)
    res := nvalue_1 + nvalue_2
    fmt.Printf("%.1f + %.1f = %.1f",
            nvalue_1, nvalue_2, res)

}
```

**输出:**

```go
0.8 + 1.0 = 1.8
```