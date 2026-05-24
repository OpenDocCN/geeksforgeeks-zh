# 求 Golang 中指定数的正弦值

> 原文:[https://www . geesforgeks . org/finding-sine-value-of-specific-number-in-golang/](https://www.geeksforgeeks.org/finding-sine-value-of-specified-number-in-golang/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。您可以借助**数学包**提供的 **Sin()函数**找到指定弧度参数的正弦值。因此，您需要在导入关键字的帮助下在程序中添加一个数学包来访问 Sin()函数。

**语法:**

```go
func Sin(y float64) float64
```

*   如果在这个函数中传递+Inf 或-Inf，那么这个函数将返回 NaN(不是数字)。
*   如果在这个函数中传递 NaN，那么这个函数将返回 NaN。
*   如果在此函数中传递 0，则此函数将返回 0。

**例 1:**

```go
// Golang program to illustrate how to find
// the sine of the given radian argument

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding the sine
    // of the given value
    // Using Sin() function
    res_1 := math.Sin(math.Pi / 4)
    res_2 := math.Sin(math.Inf(-3))
    res_3 := math.Sin(0)
    res_4 := math.Sin(math.NaN())
    res_5 := math.Sin(math.Pi)

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
Result 1: 0.7
Result 2: NaN
Result 3: 0.0
Result 4: NaN
Result 5: 0.0

```

**例 2:**

```go
// Golang program to illustrate how to find
// the sine of the given radian argument

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding sine of the given number
    nvalue_1 := math.Sin(math.Pi / 3)
    nvalue_2 := math.Sin(math.Pi / 2)

    // Sum of the given values
    res := nvalue_1 + nvalue_2

    // Displaying results
    fmt.Printf("%.1f + %.1f = %.1f", 
           nvalue_1, nvalue_2, res)

}
```

**输出:**

```go
0.9 + 1.0 = 1.9
```