# 求 Golang 中两个数的最小值

> 原文:[https://www . geesforgeks . org/find-最少两个数字 in-golang/](https://www.geeksforgeeks.org/finding-minimum-of-two-numbers-in-golang/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。借助**数学包**提供的 **Min()函数**，可以在给定的两个数字中找到最小的数字。因此，您需要在导入关键字的帮助下在程序中添加一个数学包来访问 Min()函数。

**语法:**

```go
func Min(a, b float64) float64
```

*   如果在这个函数中像 Min(-Inf，b)或 Min(a，-Inf)一样传递-Inf，那么这个函数将返回-Inf。
*   如果在这个函数中像 Min(NaN，b)或 Min(a，NaN)一样传递 NaN，那么这个函数将返回 NaN。
*   如果您在此函数中传递-0 或+0，如 Min(-0，-0)或 Min(-0，+0)或 Min(-0，-0)或 Min(+0，-0)，则此函数将返回-0。

**例 1:**

```go
// Golang program to illustrate how
// to find the smallest number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding smallest number 
    // among the given numbers
    // Using Min() function
    res_1 := math.Min(0, -0)
    res_2 := math.Min(-100, 100)
    res_3 := math.Min(45.6, 8.9)
    res_4 := math.Min(math.NaN(), 67)

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
Result 2: -100.0
Result 3: 8.9
Result 4: NaN

```

**例 2:**

```go
// Golang program to illustrate how
// to find the smallest number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding smallest number
    // among the given numbers
    // Using Min() function
    nvalue_1 := math.Min(34, 67)
    nvalue_2 := math.Min(56.7, 90.8)

    // Adding minimum numbers
    res := nvalue_1 + nvalue_2
    fmt.Printf("%.2f + %.2f = %.2f", 
           nvalue_1, nvalue_2, res)

}
```

**输出:**

```go
34.00 + 56.70 = 90.70
```