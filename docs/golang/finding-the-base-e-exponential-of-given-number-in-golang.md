# 求 Golang 中给定数的基指数

> 原文:[https://www . geesforgeks . org/find-base-e-index-of-number-in-golang/](https://www.geeksforgeeks.org/finding-the-base-e-exponential-of-given-number-in-golang/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。借助**数学包**提供的 **Exp()函数**，您可以找到指定数字的基数 e 指数，即 **e**a** 。因此，您需要在导入关键字的帮助下在程序中添加一个数学包来访问 Exp()函数。

**语法:**

```go
func Exp(a float64) float64
```

*   如果在这个函数中传递+Inf，那么这个函数将返回+Inf。
*   在这个函数中，非常大的值溢出到 0 或+Inf，非常小的值下溢到 1。
*   如果在这个函数中传递 NaN，那么这个函数将返回 NaN。

**例 1:**

```go
// Golang program to illustrate how to
// find exponential of the given number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding base-e exponential
    // of the given number
    // Using Exp() function
    res_1 := math.Exp(3)
    res_2 := math.Exp(1)
    res_3 := math.Exp(math.Inf(1))
    res_4 := math.Exp(math.NaN())

    // Displaying the result
    fmt.Printf("Result 1: %.1f", res_1)
    fmt.Printf("\nResult 2: %.1f", res_2)
    fmt.Printf("\nResult 3: %.1f", res_3)
    fmt.Printf("\nResult 4: %.1f", res_4)

}
```

**输出:**

```go
Result 1: 20.1
Result 2: 2.7
Result 3: +Inf
Result 4: NaN

```

**例 2:**

```go
// Golang program to illustrate how to
// find exponential of the given number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding base-e exponential
    // Using Exp() function
    nvalue_1 := math.Exp(2)
    nvalue_2 := math.Exp(3)
    res := nvalue_1 + nvalue_2
    fmt.Printf("%.1f + %.1f = %.1f",
            nvalue_1, nvalue_2, res)

}
```

**输出:**

```go
7.4 + 20.1 = 27.5
```