# 求 Golang 中给定数的二进制指数

> 原文:[https://www . geesforgeks . org/find-二进制-给定数的指数 in-golang/](https://www.geeksforgeeks.org/finding-binary-exponent-of-given-number-in-golang/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。您可以借助**数学包**提供的 **Logb()函数**找到指定数字的二进制指数。因此，您需要在程序中添加一个数学包，借助 import 关键字来访问 Logb()函数。

**语法:**

```go
func Logb(a float64) float64
```

*   如果在这个函数中传递+Inf 或-Inf，那么这个函数将返回+Inf。
*   如果在这个函数中传递 0，那么这个函数将返回-Inf。
*   如果在这个函数中传递 NaN，那么这个函数将返回 NaN。

**例 1:**

```go
// Golang program to illustrate how to find the
// binary exponent of the given number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding binary exponent 
    // of the given number
    // Using Logb() function
    res_1 := math.Logb(0)
    res_2 := math.Logb(1)
    res_3 := math.Logb(math.Inf(1))
    res_4 := math.Logb(math.NaN())
    res_5 := math.Logb(36)

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
Result 5: 5.0

```

**例 2:**

```go
// Golang program to illustrate how to find the
// binary exponent of the given number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding binary exponent
    // of the given number
    // Using Logb() function
    nvalue_1 := math.Logb(100)
    nvalue_2 := math.Logb(26)
    res := nvalue_1 + nvalue_2
    fmt.Printf("%.5f + %.5f = %.5f",
            nvalue_1, nvalue_2, res)

}
```

**输出:**

```go
6.00000 + 4.00000 = 10.00000
```