# 求 Golang 中指定数的反正弦

> 原文:[https://www . geesforgeks . org/find-arcsine-of-the-specific-number-in-golang/](https://www.geeksforgeeks.org/finding-arcsine-of-the-specified-number-in-golang/)

Go 语言在**数学包**的帮助下，为基本常数和数学函数提供了对数字进行运算的内置支持。借助数学包提供的 **Asin()函数**，可以找到指定数字的反正弦。因此，您需要在导入关键字的帮助下在程序中添加一个数学包来访问 Asin()函数。

**语法:**

```go
func Asin(y float64) float64
```

*   如果 y 的值< -1 or y >为 1，那么 Asin(y) = NaN
*   如果在此函数中传递 0，则此函数将返回 0。

**例 1:**

```go
// Golang program to illustrate how
// to find arcsine of the given number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding arcsine of the given value
    // Using Asin() function
    res_1 := math.Asin(1)
    res_2 := math.Asin(-1)
    res_3 := math.Asin(0)
    res_4 := math.Asin(3)

    // Displaying the result
    fmt.Printf("Result 1: %.1f", res_1)
    fmt.Printf("\nResult 2: %.1f", res_2)
    fmt.Printf("\nResult 3: %.1f", res_3)
    fmt.Printf("\nResult 4: %.1f", res_4)
}
```

**输出:**

```go
Result 1: 1.6
Result 2: -1.6
Result 3: 0.0
Result 4: NaN

```

**例 2:**

```go
// Golang program to illustrate how
// to find arcsine of the given number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding arcsine 
    // of the given value
    nvalue_1 := math.Asin(1)
    nvalue_2 := math.Asin(-1)

    // Sum of the given values
    res := nvalue_1 + nvalue_2

    // Displaying results
    fmt.Printf("%.1f + %.1f = %.1f", 
           nvalue_1, nvalue_2, res)

}
```

**输出:**

```go
1.6 + -1.6 = 0.0
```