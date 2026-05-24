# 在 Golang 中找到一个数的基数-2 指数

> 原文:[https://www . geeksforgeeks . org/find-base-2-golang 中数字的指数/](https://www.geeksforgeeks.org/finding-base-2-exponential-of-a-number-in-golang/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。借助**数学包**提供的 **Exp2()函数**，您可以找到指定数字的基数-2 指数，即 *2**a* 。因此，您需要在程序中添加一个数学包，借助 import 关键字来访问 Exp2()函数。

**语法:**

```go
func Exp2(a float64) float64
```

*   如果在这个函数中传递+Inf，那么这个函数将返回+Inf。
*   如果在这个函数中传递 NaN，那么这个函数将返回 NaN。

**例 1:**

```go
// Golang program to illustrate how to find
// base-2 exponential of the given number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding base-2 exponential 
    // of the given number
    // Using Exp2() function
    res_1 := math.Exp2(3)
    res_2 := math.Exp2(-1)
    res_3 := math.Exp2(math.Inf(1))
    res_4 := math.Exp2(math.NaN())

    // Displaying the result
    fmt.Printf("Result 1: %.1f", res_1)
    fmt.Printf("\nResult 2: %.1f", res_2)
    fmt.Printf("\nResult 3: %.1f", res_3)
    fmt.Printf("\nResult 4: %.1f", res_4)

}
```

**输出:**

```go
Result 1: 8.0
Result 2: 0.5
Result 3: +Inf
Result 4: NaN

```

**例 2:**

```go
// Golang program to illustrate how to find
// base-2 exponential of the given number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding base-2 exponential
    // Using Exp2() function
    nvalue_1 := math.Exp2(7.3)
    nvalue_2 := math.Exp2(-3)
    res := nvalue_1 + nvalue_2
    fmt.Printf("%.1f + %.1f = %.1f",
            nvalue_1, nvalue_2, res)

}
```

**输出:**

```go
157.6 + 0.1 = 157.7 
```