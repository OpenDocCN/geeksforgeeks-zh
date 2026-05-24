# 求 Golang 中给定数的平方根

> 原文:[https://www . geesforgeks . org/find-给定数字的平方根-in-golang/](https://www.geeksforgeeks.org/finding-the-square-root-of-given-number-in-golang/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。您可以借助**数学包**提供的 **Sqrt()函数**找到指定数字的平方根。因此，您需要借助 import 关键字在程序中添加一个数学包来访问 Sqrt()函数。

**语法:**

```go
func Sqrt(a float64) float64
```

*   如果在这个函数中传递+Inf，那么这个函数将返回+Inf。
*   如果在此函数中传递+0 或-0，则此函数将返回+0 或-0。
*   如果 a 的值
*   如果在这个函数中传递 NaN，那么这个函数将返回 NaN。

**例 1:**

```go
// Golang program to illustrate how to find
// the square root of the given number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding square root 
    // of the given number
    // Using Sqrt() function
    res_1 := math.Sqrt(0)
    res_2 := math.Sqrt(-100)
    res_3 := math.Sqrt(math.Inf(1))
    res_4 := math.Sqrt(math.NaN())
    res_5 := math.Sqrt(36)

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
Result 2: NaN
Result 3: +Inf
Result 4: NaN
Result 5: 6.0

```

**例 2:**

```go
// Golang program to illustrate how to find
// the square root of the given number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding square root 
    // of the given number
    // Using Sqrt() function
    nvalue_1 := math.Sqrt(100)
    nvalue_2 := math.Sqrt(25)
    res := nvalue_1 + nvalue_2
    fmt.Printf("%.3f + %.3f = %.3f",
            nvalue_1, nvalue_2, res)

}
```

**输出:**

```go
10.000 + 5.000 = 15.000
```