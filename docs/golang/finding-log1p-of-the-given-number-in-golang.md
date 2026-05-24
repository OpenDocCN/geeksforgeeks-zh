# 求 Golang 中给定数的 Log1p()

> 原文:[https://www . geesforgeks . org/find-log1p-of-the-given-number-in-golang/](https://www.geeksforgeeks.org/finding-log1p-of-the-given-number-in-golang/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。借助于**数学包**提供的 **Log1p()函数**，您可以找到 1 加上其指定参数的自然对数。因此，您需要借助 import 关键字在程序中添加一个数学包来访问 Log1p()函数。

**语法:**

```go
func Log1p(a float64) float64
```

*   当 a 的值接近零时，它比 log(a+1)精确得多。
*   如果在这个函数中传递+Inf，那么这个函数将返回+Inf。
*   如果在此函数中传递+0 或-0，则此函数将返回+0 或-0。
*   如果在这个函数中传递-1，那么这个函数将返回-Inf。
*   如果 a 的值
*   如果在这个函数中传递 NaN，那么这个函数将返回 NaN。

**例 1:**

```go
// Golang program to illustrate how to find the
// natural logarithm of plus 1 of the given number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding natural logarithm of
    // plus 1 of the given number
    // Using Logb() function
    res_1 := math.Log1p(0)
    res_2 := math.Log1p(1)
    res_3 := math.Log1p(math.Inf(1))
    res_4 := math.Log1p(math.NaN())
    res_5 := math.Log1p(36)

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
Result 1: 0.0
Result 2: 0.7
Result 3: +Inf
Result 4: NaN
Result 5: 3.6

```

**例 2:**

```go
// Golang program to illustrate how to find the
// natural logarithm of plus 1 of the given number

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding natural logarithm of
    // plus 1 of the given number
    // Using Log1p() function
    nvalue_1 := math.Log1p(100)
    nvalue_2 := math.Log1p(26)
    res := nvalue_1 + nvalue_2
    fmt.Printf("%.5f + %.5f = %.5f", 
            nvalue_1, nvalue_2, res)

}
```

**输出:**

```go
4.61512 + 3.29584 = 7.91096
```