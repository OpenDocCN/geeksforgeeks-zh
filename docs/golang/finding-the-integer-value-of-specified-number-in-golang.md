# 在 Golang 中找到指定数字的整数值

> 原文:[https://www . geesforgeks . org/find-指定数字的整数值 in-golang/](https://www.geeksforgeeks.org/finding-the-integer-value-of-specified-number-in-golang/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。借助**数学包**提供的 **Trunc()函数**，可以找到指定数字的整数值。因此，您需要借助 import 关键字在程序中添加一个数学包来访问 Trunc()函数。

**语法:**

```go
 func Trunc(a float64) float64
```

*   如果在这个函数中像 Trunc(-Inf)或 Trunc(+Inf)一样传递-Inf 或+Inf，那么这个函数将返回-Inf 或+Inf。
*   如果在此函数中传递-0 或+0，如 Trunc(-0)或 Trunc(+0)，则此函数将返回-0 或+0。
*   如果在这个函数中像 Trunc(NaN)一样传递 NaN，那么这个函数将返回 NaN。

**例 1:**

```go
// Golang program to illustrate how to
// get the integer value of the given numbers

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding the integer 
    // value of the given numbers
    // Using Trunc() function
    res_1 := math.Trunc(45.98)
    res_2 := math.Trunc(-119.98)
    res_3 := math.Trunc(math.Inf(-1))
    res_4 := math.Trunc(math.NaN())
    res_5 := math.Trunc(math.Pi)

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
Result 1: 45.0
Result 2: -119.0
Result 3: -Inf
Result 4: NaN
Result 5: 3.0

```

**例 2:**

```go
// Golang program to illustrate how to get
// the integer value of the given numbers

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding the integer value
    // of the given numbers
    // Using Trunc() function
    nvalue_1 := math.Trunc(59.89)
    nvalue_2 := math.Trunc(-7.567)

    // Sum of the given numbers
    res := nvalue_1 + nvalue_2
    fmt.Printf("%.2f + %.2f = %.2f",
           nvalue_1, nvalue_2, res)

}
```

**输出:**

```go
59.00 + -7.00 = 52.00
```