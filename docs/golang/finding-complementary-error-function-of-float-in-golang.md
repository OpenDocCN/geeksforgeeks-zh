# 求 Golang 中浮点数的互补误差函数

> 原文:[https://www . geesforgeks . org/find-complex-error-of-float-in-golang/](https://www.geeksforgeeks.org/finding-complementary-error-function-of-float-in-golang/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。您可以借助**数学包**提供的 **Erfc()函数**找到指定数字的互补误差函数。因此，您需要借助 import 关键字在程序中添加一个数学包来访问 Erfc()函数。

**语法:**

```go
func Erfc(a float64) float64
```

*   如果在这个函数中传递+Inf，那么这个函数将返回 0。
*   如果在这个函数中传递-Inf，那么这个函数将返回 2。
*   如果在这个函数中传递 NaN，那么这个函数将返回 NaN。

**例 1:**

```go
// Golang program to illustrate how to find
// complementary error function of the
// given number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding complementary error function
    // Using Erfc() function
    res_1 := math.Erfc(4.8)
    res_2 := math.Erfc(math.Inf(-3))
    res_3 := math.Erfc(math.Inf(3))
    res_4 := math.Erfc(math.NaN())

    // Displaying the result
    fmt.Printf("Result 1: %.1f", res_1)
    fmt.Printf("\nResult 2: %.1f", res_2)
    fmt.Printf("\nResult 3: %.1f", res_3)
    fmt.Printf("\nResult 4: %.1f", res_4)

}
```

**输出:**

```go
Result 1: 0.0
Result 2: 2.0
Result 3: 0.0
Result 4: NaN

```

**例 2:**

```go
// Golang program to illustrate how to find
// complementary error function of the
// given number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding complementary 
    // error function
    // Using Erfc() function
    nvalue_1 := math.Erfc(math.Inf(-3))
    nvalue_2 := math.Erfc(4.9)
    res := nvalue_1 + nvalue_2
    fmt.Printf("%.1f + %.1f = %.1f",
            nvalue_1, nvalue_2, res)

}
```

**输出:**

```go
2.0 + 0.0 = 2.0
```