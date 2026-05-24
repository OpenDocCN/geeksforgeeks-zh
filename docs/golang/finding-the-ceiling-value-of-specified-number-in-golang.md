# 在 Golang 中找到指定数量的上限值

> 原文:[https://www . geesforgeks . org/find-the-天花板-指定数值-in-golang/](https://www.geeksforgeeks.org/finding-the-ceiling-value-of-specified-number-in-golang/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。借助**数学包**提供的**Cell()函数**，您可以找到大于或等于指定数字的最小整数值。因此，您需要在导入关键字的帮助下在程序中添加一个数学包来访问 Ceil()函数。

**语法:**

```go
func Ceil(y float64) float64
```

*   如果在这个函数中传递+Inf 或-Inf，那么这个函数将返回+Inf 或-Inf。
*   如果在此函数中传递-0 或+0，则此函数将返回-0 或+0。
*   如果在这个函数中传递 NaN，那么这个函数将返回 NaN。

**例 1:**

```go
// Golang program to illustrate how to find
// the least integer value greater than or
// equal to the specified number
package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding the least integer value 
    // greater than or equal to the
    // given number
    // Using Ceil() function
    res_1 := math.Ceil(math.Pi / 2)
    res_2 := math.Ceil(34.567)
    res_3 := math.Ceil(-12.34)

    // Displaying the result
    fmt.Printf("Result 1: %.1f", res_1)
    fmt.Printf("\nResult 2: %.1f", res_2)
    fmt.Printf("\nResult 3: %.1f", res_3)

}
```

**输出:**

```go
Result 1: 2.0
Result 2: 35.0
Result 3: -12.0

```

**例 2:**

```go
// Golang program to illustrate how to find
// the least integer value greater than or
// equal to the specified number
package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding the least integer value
    // greater than or equal to the
    // given number
    nvalue_1 := math.Sin(math.Pi / 4)
    nvalue_2 := math.Sin(math.Pi / 6)
    res := nvalue_1 + nvalue_2

    fmt.Printf("%.1f + %.1f = %.1f",
            nvalue_1, nvalue_2, res)
    fmt.Println("\nRound off the result: ",
                            math.Ceil(res))

}
```

**输出:**

```go
0.7 + 0.5 = 1.2
Round off result:  2

```