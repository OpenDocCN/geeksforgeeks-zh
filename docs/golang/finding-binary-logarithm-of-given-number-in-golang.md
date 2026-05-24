# 求 Golang 中给定数的二进制对数

> 原文:[https://www . geesforgeks . org/find-二进制-给定对数-in-golang/](https://www.geeksforgeeks.org/finding-binary-logarithm-of-given-number-in-golang/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。您可以借助**数学包**提供的 **Log2()函数**找到指定数字的二进制对数。因此，您需要借助 import 关键字在程序中添加一个数学包来访问 Log2()函数。

**语法:**

```go
func Log2(a float64) float64
```

*   如果在这个函数中传递+Inf，那么这个函数将返回+Inf。
*   如果在这个函数中传递 0，那么这个函数将返回-Inf。
*   如果 a 的值< 0，那么这个函数将返回 NaN。
*   如果在这个函数中传递 NaN，那么这个函数将返回 NaN。

**例 1:**

```go
// Golang program to illustrate how to find the
// binary logarithm of the given number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding binary logarithm
    // of the given number
    // Using Log2() function
    res_1 := math.Log2(0)
    res_2 := math.Log2(1)
    res_3 := math.Log2(math.Inf(1))
    res_4 := math.Log2(math.NaN())
    res_5 := math.Log2(36)

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
Result 1: -Inf
Result 2: 0.0
Result 3: +Inf
Result 4: NaN
Result 5: 5.2

```

**例 2:**

```go
// Golang program to illustrate how to find the
// binary logarithm of the given number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding binary logarithm
    // of the given number
    // Using Log2() function
    nvalue_1 := math.Log2(100)
    nvalue_2 := math.Log2(26)
    res := nvalue_1 + nvalue_2
    fmt.Printf("%.5f + %.5f = %.5f",
            nvalue_1, nvalue_2, res)

}
```

**输出:**

```go
6.64386 + 4.70044 = 11.34430
```