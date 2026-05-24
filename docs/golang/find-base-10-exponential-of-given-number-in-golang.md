# 求 Golang 中给定数的基数-10 指数

> 原文:[https://www . geesforgeks . org/find-base-10-golang 中给定数字的指数/](https://www.geeksforgeeks.org/find-base-10-exponential-of-given-number-in-golang/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。借助**数学包**提供的 **pow10()函数**，可以找到指定数字的基数-10 指数(10**a)。因此，您需要在导入关键字的帮助下在程序中添加一个数学包来访问 Pow10()函数。

**语法:**

```go
func Pow10(a int) float64
```

*   如果值为
*   如果 a 的值> 308，那么这个函数将返回+Inf。

**例 1:**

```go
// Golang program to illustrate how to find
// base-10 exponential of the given numbers

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding the base-10 exponential
    // of the given numbers
    // Using Pow10() function
    res_1 := math.Pow10(3)
    res_2 := math.Pow10(-2)
    res_3 := math.Pow10(310)
    res_4 := math.Pow10(-300)

    // Displaying the result
    fmt.Printf("Result 1: %.1f", res_1)
    fmt.Printf("\nResult 2: %.1f", res_2)
    fmt.Printf("\nResult 3: %.1f", res_3)
    fmt.Printf("\nResult 4: %.1f", res_4)

}
```

**输出:**

```go
Result 1: 1000.0
Result 2: 0.0
Result 3: +Inf
Result 4: 0.0

```

**例 2:**

```go
// Golang program to illustrate how to find
// base-10 exponential of the given numbers

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding the base-10 exponential
    // of the given numbers
    // Using Pow10() function
    nvalue_1 := math.Pow10(2)
    nvalue_2 := math.Pow10(3)

    // Sum of the given exponentials
    res := nvalue_1 + nvalue_2
    fmt.Printf("%.2f + %.2f = %.2f", 
            nvalue_1, nvalue_2, res)

}
```

**输出:**

```go
100.00 + 1000.00 = 1100.00
```