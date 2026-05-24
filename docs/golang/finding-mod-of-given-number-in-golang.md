# 在 Golang 中找到给定数量的 Mod

> 原文:[https://www . geeksforgeeks . org/find-mod-of-given-number-in-golang/](https://www.geeksforgeeks.org/finding-mod-of-given-number-in-golang/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。借助**数学包**提供的 **mod()函数**，可以找到指定 a/b 的 Mod 或浮点余数。因此，您需要在程序中添加一个数学包，借助 import 关键字来访问 Mod()函数。

**语法:**

```go
func Min(a, b float64) float64
```

*   在这个函数中，结果的大小小于 b，其符号与 a 的符号一致。
*   如果在这个函数中像 Mod(-Inf，b)或 Mod(+Inf，b)一样传递-Inf 或+Inf，那么这个函数将返回 NaN。
*   如果在这个函数中像 Mod(NaN，b)一样传递 NaN，那么这个函数将返回 NaN。
*   如果在这个函数中像 Mod(a，0)一样传递 b=0，那么这个函数将返回 NaN。
*   如果你在这个函数中像 Mod(a，-Inf)或 Mod(b，+Inf)一样传递-Inf 或+Inf，那么这个函数将返回一个。
*   如果在这个函数中像 Mod(a，NaN)一样传递 NaN，那么这个函数将返回 NaN。

**例 1:**

```go
// Golang program to illustrate how to
// find mod of the specified numbers

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding mod of the given numbers
    // Using Mod() function
    res_1 := math.Mod(60, 5)
    res_2 := math.Mod(-100, 100)
    res_3 := math.Mod(45.6, 8.9)
    res_4 := math.Mod(math.NaN(), 67)
    res_5 := math.Mod(math.Inf(1), 67)

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
Result 1: 0.0
Result 2: -0.0
Result 3: 1.1
Result 4: NaN
Result 5: NaN

```

**例 2:**

```go
// Golang program to illustrate how to
// find mod of the specified numbers

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding mod of 
    // the given numbers
    // Using Mod() function
    nvalue_1 := math.Mod(34, 6)
    nvalue_2 := math.Mod(56.7, 3.4)

    // Finding sum of the given mod
    res := nvalue_1 + nvalue_2
    fmt.Printf("%.2f + %.2f = %.2f", 
            nvalue_1, nvalue_2, res)

}
```

**输出:**

```go
4.00 + 2.30 = 6.30
```