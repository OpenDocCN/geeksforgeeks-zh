# 如何求 Golang 中一个数的 Sin 和 Cos 值？

> 原文:[https://www . geesforgeks . org/如何找到 golang 中数字的原值/](https://www.geeksforgeeks.org/how-to-find-the-sin-and-cos-value-of-a-number-in-golang/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。借助**数学包**提供的 **Sincos()函数**，可以找到指定数字的 sin 和 cos 的值。因此，您需要在导入关键字的帮助下在程序中添加一个数学包来访问 Sincos()函数。

**语法:**

```go
func Sincos(a float64) (sin, cos float64)
```

*   如果在这个函数中像 Sincos(-Inf)或 Sincos(+Inf)一样传递-Inf 或+Inf，那么这个函数将返回 NaN，NaN。
*   如果在这个函数中传递-0 或+0，比如 Sincos(-0)或 Sincos(+0)，那么这个函数将返回-0 或+0，1。
*   如果在这个函数中像 Sincos(NaN)一样传递 NaN，那么这个函数将返回 NaN，NaN。

**例 1:**

```go
// Golang program to illustrate the Sincos() Function

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Using Sincos() function
    res_1, res_2 := math.Sincos(math.Pi / 3)
    res_3, res_4 := math.Sincos(0)
    res_5, res_6 := math.Sincos(math.Inf(-1))
    res_7, res_8 := math.Sincos(math.NaN())
    res_9, res_10 := math.Sincos(math.Pi)

    // Displaying the result
    fmt.Printf("Result 1: %.1f, %.1f", res_1, res_2)
    fmt.Printf("\nResult 2: %.1f, %.1f", res_3, res_4)
    fmt.Printf("\nResult 3: %.1f, %.1f", res_5, res_6)
    fmt.Printf("\nResult 4: %.1f, %.1f", res_7, res_8)
    fmt.Printf("\nResult 5: %.1f, %.1f", res_9, res_10)

}
```

**输出:**

```go
Result 1: 0.9, 0.5
Result 2: 0.0, 1.0
Result 3: NaN, NaN
Result 4: NaN, NaN
Result 5: 0.0, -1.0

```

**例 2:**

```go
// Golang program to illustrate the Sincos() Function

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Using Sincos() function
    nvalue_1, nvalue_2 := math.Sincos(math.Pi / 2)
    nvalue_3, nvalue_4 := math.Sincos(math.Pi / 3)

    // Sum of the given sin values
    res1 := nvalue_1 + nvalue_3
    fmt.Println("Sum of Sin Values:")
    fmt.Printf("%.2f + %.2f = %.2f\n", 
            nvalue_1, nvalue_3, res1)

    // Sum of the given cos values
    res2 := nvalue_2 + nvalue_4
    fmt.Println("Sum of Cos Values:")
    fmt.Printf("%.2f + %.2f = %.2f", 
           nvalue_2, nvalue_4, res2)

}
```

**输出:**

```go
Sum of Sin Values:
1.00 + 0.87 = 1.87
Sum of Cos Values:
0.00 + 0.50 = 0.50

```