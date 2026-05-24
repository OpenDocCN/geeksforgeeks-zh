# 数学。Golang 中的余数()函数及示例

> 原文:[https://www . geeksforgeeks . org/math-余数-函数-in-golang-with-examples/](https://www.geeksforgeeks.org/math-remainder-function-in-golang-with-examples/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。借助**数学包**提供的**余数()函数**，可以找到 a/b 的余数或 IEEE 754 浮点余数。因此，您需要在导入关键字的帮助下，在程序中添加一个数学包，以访问余数()函数。

**语法:**

```go
func Remainder(a, b float64) float64
```

*   如果在这个函数中像余数(-Inf，b)或余数(+Inf，b)一样传递-Inf 或+Inf，那么这个函数将返回 NaN。
*   如果在这个函数中像余数(NaN，b)一样传递 NaN，那么这个函数将返回 NaN。
*   如果在这个函数中像余数(a，0)一样传递 b=0，那么这个函数将返回 NaN。
*   如果你在这个函数中像余数(a，-Inf)或余数(b，+Inf)一样传递-Inf 或+Inf，那么这个函数将返回一个。
*   如果在这个函数中像余数(a，NaN)一样传递 NaN，那么这个函数将返回 NaN。

**例 1:**

```go
// Golang program to illustrate
// math.Remainder() Function
package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding remainder
    // Using Reminder() function
    res_1 := math.Remainder(36, 5)
    res_2 := math.Remainder(-100, 100)
    res_3 := math.Remainder(45.6, 8.9)
    res_4 := math.Remainder(math.NaN(), 67)
    res_5 := math.Remainder(math.Inf(1), 67)

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
Result 1: 1.0
Result 2: -0.0
Result 3: 1.1
Result 4: NaN
Result 5: NaN

```

**例 2:**

```go
// Golang program to illustrate
// math.Remainder() Function
package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding remainder
    // Using Remainder() function
    nvalue_1 := math.Remainder(49, 6)
    nvalue_2 := math.Remainder(56.7, 3)

    // Finding sum of the
    // given remainders
    res := nvalue_1 + nvalue_2
    fmt.Printf("%.2f + %.2f = %.2f",
           nvalue_1, nvalue_2, res)

}
```

**输出:**

```go
1.00 + -0.30 = 0.70
```