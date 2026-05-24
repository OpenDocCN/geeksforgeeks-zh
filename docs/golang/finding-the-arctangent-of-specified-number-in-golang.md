# 求 Golang 中指定数的反正切

> 原文:[https://www . geesforgeks . org/find-the-arctangent-of-specific-number-in-golang/](https://www.geeksforgeeks.org/finding-the-arctangent-of-specified-number-in-golang/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。借助**数学包**提供的 **Atan()函数**，可以找到指定数字的反正切。因此，您需要在程序中添加一个数学包，借助 import 关键字来访问 Atan()函数。

**语法:**

```go
func Atan(y float64) float64
```

*   如果在这个函数中传递+Inf 或-Inf，那么这个函数将返回+Pi/2 或-Pi/2。
*   如果在此函数中传递 0，则此函数将返回 0。

**例 1:**

```go
// Golang program to illustrate how
// to find arctangent of the given number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding arctangent of
    // the given value
    // Using Atan() function
    res_1 := math.Atan(1)
    res_2 := math.Atan(math.Inf(-3))
    res_3 := math.Atan(0)
    res_4 := math.Atan(math.NaN())

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
Result 2: -1.6
Result 3: 0.0
Result 4: NaN

```

**例 2:**

```go
// Golang program to illustrate how
// to find arctangent of the given number
package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding arctangent
    // of the given value
    nvalue_1 := math.Atan(1)
    nvalue_2 := math.Atan(-3)

    // Sum of the given values
    res := nvalue_1 + nvalue_2

    // Displaying results
    fmt.Printf("%.1f + %.1f = %.1f", 
            nvalue_1, nvalue_2, res)

}
```

**输出:**

```go
0.8 + -1.2 = -0.5
```