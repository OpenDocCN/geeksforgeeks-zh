# 复制 Golang 中给定数字的符号

> 原文:[https://www . geesforgeks . org/copy-the-sign-of-given-number-in-golang/](https://www.geeksforgeeks.org/copy-the-sign-of-given-number-in-golang/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。您可以借助**数学包**提供的 **Copysign()功能**复制指定数字的符号。因此，您需要在导入关键字的帮助下，在程序中添加一个数学包来访问 Copysign()函数。

**语法:**

```go
func Copysign(a, b float64) float64
```

这里，这个函数返回一个值，大小为 a，符号为 b。

**例 1:**

```go
// Golang program to illustrate how to
// copy the sign of the given number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Copying the sign of the
    // given numbers
    // Using Copysign() function
    res_1 := math.Copysign(2, -3)
    res_2 := math.Copysign(-8, 1)
    res_3 := math.Copysign(-67, -2)

    // Displaying the result
    fmt.Printf("Result 1: %.1f", res_1)
    fmt.Printf("\nResult 2: %.1f", res_2)
    fmt.Printf("\nResult 3: %.1f", res_3)

}
```

**输出:**

```go
Result 1: -2.0
Result 2: 8.0
Result 3: -67.0

```

**例 2:**

```go
// Golang program to illustrate how to
// copy the sign of the given number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Copying the sign of 
    // the given numbers
    // Using Copysign() function
    nvalue_1 := math.Copysign(3, -1)
    nvalue_2 := math.Copysign(-4, 3)
    res := nvalue_1 + nvalue_2
    fmt.Printf("%.1f + %.1f = %.1f",
          nvalue_1, nvalue_2, res)

}
```

**输出:**

```go
-3.0 + 4.0 = 1.0
```