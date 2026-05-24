# 数学。Golang 中的 RoundToEven()函数及示例

> 原文:[https://www . geesforgeks . org/math-roughoeven-function-in-golang-with-examples/](https://www.geeksforgeeks.org/math-roundtoeven-function-in-golang-with-examples/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。借助**数学包**提供的**round oeven()函数**，可以将给定的数字四舍五入为最接近的偶数。因此，您需要借助 import 关键字在程序中添加一个数学包来访问 RoundToEven()函数。

**语法:**

```go
func RoundToEven(a float64) float64
```

*   如果在这个函数中传递-Inf 或+Inf，比如 RoutHoeven(-Inf)或 RoutHoeven(+Inf)，那么这个函数将返回-Inf 或+Inf。
*   如果在像 RoutHoeven(-0)或 RoutHoeven(+0)这样的函数中传递-0 或+0，那么这个函数将返回-0 或+0。
*   如果在像 RoutHoeven(NaN)这样的函数中传递 NaN，那么这个函数将返回 NAn。

**例 1:**

```go
// Golang program to illustrate how to round
// off the given number to nearest even integer

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Using RoundToEven() function
    res_1 := math.RoundToEven(45.98)
    res_2 := math.RoundToEven(-119.98)
    res_3 := math.RoundToEven(math.Inf(-1))
    res_4 := math.RoundToEven(math.NaN())
    res_5 := math.RoundToEven(math.Inf(1))

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
Result 1: 46.0
Result 2: -120.0
Result 3: -Inf
Result 4: NaN
Result 5: +Inf

```

**例 2:**

```go
// Golang program to illustrate how to round
// off the given number to nearest even integer

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Using RoundToEven() function
    nvalue_1 := math.RoundToEven(59.89)
    nvalue_2 := math.RoundToEven(-7.567)

    // Sum of the given numbers
    res := nvalue_1 + nvalue_2
    fmt.Printf("%.2f + %.2f = %.2f",
            nvalue_1, nvalue_2, res)

}
```

**输出:**

```go
60.00 + -8.00 = 52.00
```