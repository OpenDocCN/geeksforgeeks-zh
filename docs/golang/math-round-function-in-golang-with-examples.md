# 数学。Golang 中的 Round()函数示例

> 原文:[https://www . geesforgeks . org/math-round-function-in-golang-with-examples/](https://www.geeksforgeeks.org/math-round-function-in-golang-with-examples/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。借助**数学包**提供的 **Round()函数**，可以将给定的数字四舍五入到最接近的整数(四舍五入到离零一半)。因此，您需要在导入关键字的帮助下在程序中添加一个数学包来访问 Round()函数。

**语法:**

```go
func Round(a float64) float64
```

*   如果在这个函数中像 Round(-Inf)或 Round(+Inf)一样传递-Inf 或+Inf，那么这个函数将返回-Inf 或+Inf。
*   如果在此函数中传递-0 或+0，如 Round(-0)或 Round(+0)，则此函数将返回-0 或+0。
*   如果在这个函数中像 Round(NaN)一样传递 NaN，那么这个函数将返回 NaN。

**例 1:**

```go
// Golang program to illustrate how to
// round off the given number to the 
// nearest integer

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding the nearest integer
    // of the given numbers
    // Using Round() function
    res_1 := math.Round(36.98)
    res_2 := math.Round(-100.98)
    res_3 := math.Round(math.Inf(-1))
    res_4 := math.Round(math.NaN())
    res_5 := math.Round(math.Inf(1))

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
Result 1: 37.0
Result 2: -101.0
Result 3: -Inf
Result 4: NaN
Result 5: +Inf

```

**例 2:**

```go
// Golang program to illustrate how to
// round off the given number to the
// nearest integer

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding the nearest integer
    // of the given numbers
    // Using Round() function
    nvalue_1 := math.Round(49.89)
    nvalue_2 := math.Round(-4.567)

    // Finding sum of the given numbers
    res := nvalue_1 + nvalue_2
    fmt.Printf("%.2f + %.2f = %.2f",
           nvalue_1, nvalue_2, res)

}
```

**输出:**

```go
50.00 + -5.00 = 45.00
```