# 求 Golang 中两个数的最大值

> 原文:[https://www . geesforgeks . org/find-golang 中两个数字的最大值/](https://www.geeksforgeeks.org/finding-maximum-of-two-numbers-in-golang/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。借助数学包提供的 **Max()函数**，可以在给定的两个数字中找到最大的数字。所以，你需要在程序中添加一个数学包，借助 import 关键字来访问 *Max()函数*。
**语法:**

```go
func Max(a, b float64) float64
```

*   如果你在这个函数中像 Max(+Inf，b)或者 Max(a，+Inf)一样传递+Inf，那么这个函数将返回+Inf。
*   如果在这个函数中像 Max(NaN，b)或 Max(a，NaN)一样传递 NaN，那么这个函数将返回 NaN。
*   如果在这个函数中像 Max(-0，-0)一样传递-0，那么这个函数将返回-0。
*   如果在此函数中传递-0 或+0，如 Max(+0，-0)或 Max(+0，+0)或 Max(-0，+0)或 Max(+0，+0)，则此函数将返回+0。

**例 1:**

## C

```go
// Golang program to illustrate
// how to find the largest number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding largest number
    // among the given numbers
    // Using Max() function
    res_1 := math.Max(0, -0)
    res_2 := math.Max(-100, 100)
    res_3 := math.Max(45.6, 8.9)
    res_4 := math.Max(math.NaN(), 67)

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
Result 2: 100.0
Result 3: 45.6
Result 4: NaN
```

**例 2:**

## C

```go
// Golang program to illustrate
// how to find the largest number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding largest number
    // among the given numbers
    // Using Max() function
    nvalue_1 := math.Max(34, 67)
    nvalue_2 := math.Max(56.7, 90.8)

    // Adding maximum numbers
    res := nvalue_1 + nvalue_2
    fmt.Printf("%.2f + %.2f = %.2f",
            nvalue_1, nvalue_2, res)

}
```

**输出:**

```go
67.00 + 90.80 = 157.80
```