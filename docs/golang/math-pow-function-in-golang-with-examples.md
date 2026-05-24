# 数学。Golang 中的 Pow()函数示例

> 原文:[https://www . geesforgeks . org/math-power-function-in-golang-with-examples/](https://www.geeksforgeeks.org/math-pow-function-in-golang-with-examples/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。借助数学包提供的 **Pow()函数**，可以找到 b(a**b)的基数-a 指数。所以，需要在程序中添加一个数学包，借助 import 关键字来访问 Pow()函数。

**语法:**

```go
func Pow(a, b float64) float64
```

*   如果幂(a，0)，那么这个方法将为任何 a 返回 1
*   如果 Pow(1，b)，那么这个方法将为任何 b 返回 1
*   如果 Pow(a，1)，那么这个方法将为任何 a 返回一个
*   如果 Pow(NaN，b)，那么这个方法将返回 NaN。
*   如果 Pow(a，NaN)，那么这个方法将返回 NaN。
*   如果 Pow( 0，b)，那么这个方法将为 b 返回一个奇数< 0 的 Inf。
*   如果 Pow( 0，-Inf)，那么这个方法将返回+Inf。
*   如果 Pow( 0，+Inf)，那么这个方法将返回+0。
*   如果 Pow( 0，b)，那么这个方法将返回有限 b < 0 的+Inf，而不是奇数。
*   如果幂(0，b)，那么这个方法将为 b 返回 0，b 是一个大于 0 的奇数。
*   如果 Pow( 0，b)，那么这个方法将返回有限 b > 0 的+0，而不是奇数。
*   如果 Pow(+1，Inf)，那么这个方法将返回 1。
*   如果 Pow(a，+Inf)，那么这个方法将为|a| > 1 返回+Inf。
*   如果 Pow(a，-Inf)，那么这个方法将为|a| > 1 返回+0。
*   如果 Pow(a，+Inf)，则此方法将为|a| < 1 返回+0。
*   如果 Pow(a，-Inf)，那么这个方法将为|a| < 1 返回+Inf。
*   如果 Pow(+Inf，b)，那么这个方法将为 b > 0 返回+Inf。
*   如果 Pow(+Inf，b)，那么对于 b < 0，这个方法将返回+0。
*   如果 Pow(-Inf，b)，那么这个方法将返回 Pow(-0，-b)。
*   如果 Pow(a，b)，那么这个方法将返回有限 a < 0 和有限非整数 b 的 NaN。

**例 1:**

```go
// Golang program to illustrate
// the use of math.Pow() function

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding the base-a exponential of b
    // Using Pow() function
    res_1 := math.Pow(3, 5)
    res_2 := math.Pow(math.Inf(1), 3)
    res_3 := math.Pow(2, 0)
    res_4 := math.Pow(1, math.NaN())
    res_5 := math.Pow(-0, math.Inf(-1))

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
Result 1: 243.0
Result 2: +Inf
Result 3: 1.0
Result 4: 1.0
Result 5: +Inf

```

**例 2:**

```go
// Golang program to illustrate
// the use of math.Pow() function

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding the base-a exponential of b
    // Using Pow() function
    nvalue_1 := math.Pow(3, 4)
    nvalue_2 := math.Pow(5, 6)

    // Sum of the given numbers
    res := nvalue_1 + nvalue_2
    fmt.Printf("%.3f + %.3f = %.3f",
            nvalue_1, nvalue_2, res)

}
```

**输出:**

```go
81.000 + 15625.000 = 15706.000
```