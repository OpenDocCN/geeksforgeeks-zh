# Golang 中给定数的逆误差函数

> 原文:[https://www . geesforgeks . org/golang 中给定数字的逆错误函数/](https://www.geeksforgeeks.org/inverse-error-function-of-given-number-in-golang/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。您可以借助**数学包**提供的 **Erfinv()函数**找到指定数字的逆误差函数。因此，您需要在 import 关键字的帮助下，在程序中添加一个数学包来访问 Erfinv()函数。

**语法:**

```go
func Erfinv(a float64) float64
```

*   如果在这个函数中传递 1，那么这个函数将返回+Inf。
*   如果在这个函数中传递-1，那么这个函数将返回-Inf。
*   如果在这个函数中传递 NaN，那么这个函数将返回 NaN。
*   如果这个函数中< -1 or a >的值为 1，那么这个函数将返回 NaN。

**例 1:**

```go
// Golang program to illustrate how to find
// the inverse error function of the
// given number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding inverse error function
    // Using Erfinv() function
    res_1 := math.Erfinv(0.968)
    res_2 := math.Erfinv(1)
    res_3 := math.Erfinv(-1)
    res_4 := math.Erfinv(math.NaN())

    // Displaying the result
    fmt.Printf("Result 1: %.1f", res_1)
    fmt.Printf("\nResult 2: %.1f", res_2)
    fmt.Printf("\nResult 3: %.1f", res_3)
    fmt.Printf("\nResult 4: %.1f", res_4)

}
```

**输出:**

```go
Result 1: 1.5
Result 2: +Inf
Result 3: -Inf
Result 4: NaN

```

**例 2:**

```go
// Golang program to illustrate how to find
// the inverse error function of the
// given number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding inverse error function
    // Using Erfc() function
    nvalue_1 := math.Erfinv(0.5475)
    nvalue_2 := math.Erfinv(0.28547)
    res := nvalue_1 + nvalue_2
    fmt.Printf("%.1f + %.1f = %.1f",
            nvalue_1, nvalue_2, res)

}
```

**输出:**

```go
0.5 + 0.3 = 0.8
```