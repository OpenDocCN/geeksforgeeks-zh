# 求 Golang 中指定数的反余弦

> 原文:[https://www . geeksforgeeks . org/find-the-arc-cosine-of-specific-number-in-golang/](https://www.geeksforgeeks.org/finding-the-arccosine-of-specified-number-in-golang/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。您可以借助**数学包**提供的 **Acos()函数**找到指定数字的反余弦。因此，您需要在导入关键字的帮助下在程序中添加一个数学包来访问 Acos()函数。

**语法:**

```go
func Acos(y float64) float64
```

如果 y 的值< -1 or y >为 1，那么 Acos(y) = NaN

**例 1:**

```go
// Golang program to illustrate how to
// find arccosine of the given number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding arccosine of
    // the given value
    // Using Acos() function
    res_1 := math.Acos(1)
    res_2 := math.Acos(-1)
    res_3 := math.Acos(3.3)

    // Displaying the result
    fmt.Printf("Result 1: %.1f", res_1)
    fmt.Printf("\nResult 2: %.1f", res_2)
    fmt.Printf("\nResult 3: %.1f", res_3)
}
```

**输出:**

```go
Result 1: 0.0
Result 2: 3.1
Result 3: NaN

```

**例 2:**

```go
// Golang program to illustrate how to
// find arccosine of the given number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding arccosine
    // of the given value
    nvalue_1 := math.Acos(1)
    nvalue_2 := math.Acos(-1)

    // Sum of the given values
    res := nvalue_1 + nvalue_2

    // Displaying results
    fmt.Printf("%.1f + %.1f = %.1f",
            nvalue_1, nvalue_2, res)

}
```

**输出:**

```go
0.0 + 3.1 = 3.1
```